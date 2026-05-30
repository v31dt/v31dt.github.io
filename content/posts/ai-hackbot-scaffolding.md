---
title: "AI Hackbot Scaffolding"
date: 2026-05-30
draft: false
description: "Follow-up research note to my podcast episode on AI hackbots, focused on how much scaffolding is actually needed when frontier models are already strong."
tags: ["ai", "bug-bounty", "automation", "security-research", "hackbot"]
---

This is a follow-up to my podcast episode, [Future of Bug Bounty and How to Build Your Own HackBot](/posts/podcast-episode/). After that conversation, I kept thinking about the practical question behind the whole idea: now that the models are getting so strong, how much scaffolding do you actually need?

My current conclusion for black-box bug bounty and security testing is this:

**A small, sane scaffold gets you around 60-80% of the practical benefit of a much bigger system.**

Not an `md` file that says "try harder." I mean something more concrete: persistent target memory, a coverage map, a validation gate, an evidence template, and a retry/critic loop.

## Rough multiplier estimates

| Setup | Valid unique findings per analyst-hour | Confidence |
| --- | ---: | --- |
| Vanilla Claude Code / raw agent | 1.0x baseline | Medium |
| Generic prompt file | 1.05-1.2x | Medium-high |
| Good lightweight scaffold | 1.4-2.5x | Medium |
| Strong scaffold + tool loop + validation | 2-4x | Medium |
| Full integrated system | 3-10x vs vanilla, usually 1.5-4x vs good scaffold | Low-medium |

The public 2026 numbers are messy, but the direction is clear. XBOW's evaluation of Anthropic's Mythos Preview is a useful black-box clue because it separates raw model capability from orchestration, tooling, and live-site interaction. Their write-up says live-site interaction can matter more than source access for exploit validation, and reports Mythos cutting false negatives by 42% compared with Opus 4.6 on a web exploit benchmark, 55% with source available. Anthropic's Project Glasswing update points in the same direction from the source-code side: discovery is getting easier, while verification, disclosure, and patching become the bottleneck.

So the question is not "Can the model think?" Increasingly, yes. The question is whether the system around it stops wasting cycles and forces evidence.

## The 20% that gets 80%

For black-box work, the best return is not more prompts. It is making the agent remember what happened and prove what it claims.

The optimal lightweight scaffold starts with:

1. **Persistent target state**

   One `target.md` or small database containing assets, roles, auth states, endpoints, tech stack, known dead ends, tested areas, and interesting observations. This alone is a big jump because vanilla agents repeatedly rediscover the same facts.

2. **Coverage map**

   Track feature, endpoint/API, parameters, auth role, tested vulnerability classes, and result. The point is not fancy automation. The point is preventing random, vibes-based testing.

3. **Hypothesis queue**

   Every task should become: given the current target state, generate a few plausible hypotheses, pick one, test it, record the result, and update state.

4. **Validation gate before report**

   Require reproducible steps, exact request/response or UI path, impact, affected role, why it is not intended behaviour, and negative controls. This is where most AI-generated bug-hunting output dies.

5. **Critic / falsifier pass**

   A second pass tries to disprove the bug: duplicate, self-XSS, missing auth assumption, admin-only requirement, rate-limit artefact, browser cache, test-account-only behaviour, or anything else that would kill the report.

6. **Evidence template**

   Force every candidate into a report skeleton. If it cannot fill the skeleton, it is not a finding yet.

That is the 20%. Not multi-agent theatre.

## Where the gains come from

Rough weighting for black-box work:

| Component | Share of useful improvement |
| --- | ---: |
| Persistent target memory / coverage tracking | 30-35% |
| Validation and evidence gates | 25-30% |
| Tool/execution loop around browser/proxy/API requests | 20-25% |
| Vulnerability-class playbooks | 10-15% |
| Multi-agent debate / "try harder" prompting | 5-10% |

The highest-ROI core is the memory + coverage + validation loop.

## What changes as models get better?

As models improve, prompt scaffolding loses relative value. A frontier model needs less hand-holding about "thinking like a hacker."

But system scaffolding keeps value because it gives the model things raw intelligence does not automatically have:

- persistent memory across sessions;
- exact target state;
- replayable evidence;
- auth/session management;
- coverage accounting;
- safe live-site interaction;
- deduplication;
- validation discipline.

The future-proof bet is not a huge prompt library. It is a thin harness that makes any better model more productive.

## Recommended architecture

For a solo black-box hunter, the optimal starting point is not a big XBOW-style system. It is this:

```text
target.md
coverage.md
hypotheses.md
findings.md
dead-ends.md
report-template.md
critic-checklist.md
```

Then run the agent in this loop:

```text
Read target state.
Pick one untested surface.
Generate hypotheses.
Test one hypothesis.
Record exact evidence.
Update coverage.
Criticize the candidate.
Either discard, continue testing, or draft report.
```

That probably gets most of the benefit of a larger system for a fraction of the engineering cost. The remaining gains come from harder pieces: browser/proxy automation, role/account orchestration, replayable PoC generation, distributed scanning, ranking, deduplication, and continuous retesting.

## Agent count

For this kind of scaffold, many autonomous agents are not the optimal starting point.

The best quality-per-dollar setup is:

```text
one persistent operator
one stateless verifier
one cheap report formatter
```

The operator owns the loop and has write authority over the target state, coverage, hypotheses, and findings. The verifier is only called when there is a candidate finding. Its job is to disprove the bug, not to find new ones. The report formatter only runs after validation.

Multiple agents are useful for sequential specialization, not for a swarm. More agents usually means more token burn, more state conflicts, and more duplicated work.

## Required gates

A candidate cannot enter `findings.md` unless it has:

```text
affected asset
affected role/account
exact endpoint or UI path
repro steps
request/response or observable proof
expected behavior
actual behavior
impact
negative control
scope check
duplicate check
```

The verifier must return one of:

```text
PASS
FAIL
NEEDS_MORE_EVIDENCE
OUT_OF_SCOPE
DUPLICATE_RISK
LOW_IMPACT
```

If it says `NEEDS_MORE_EVIDENCE`, it must give exact tests to run.

## Model-agnostic by design

This should be model-agnostic over HTTP from day one. The core should not care whether the model is Claude, GPT, Gemini, Qwen, DeepSeek, or something local.

The durable part is:

```text
state
coverage
evidence
validation gates
tool execution
replayability
report quality
```

Models will keep improving. The scaffold should let better models drop in underneath it.

Public references:

- [XBOW: Mythos for Offensive Security](https://xbow.com/blog/mythos-offensive-security-xbow-evaluation)
- [Anthropic: Project Glasswing initial update](https://www.anthropic.com/research/glasswing-initial-update?facet1=startup)
