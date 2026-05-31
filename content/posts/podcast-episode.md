---
title: "Future of Bug Bounty and How to Build Your Own HackBot"
date: 2026-05-25
draft: false
hidden: false
description: "A podcast conversation with Pedro Paniago about AI, bug bounty, offensive security, learning, and the architecture behind a useful hackbot."
tags: ["podcast", "communication", "professional-networking"]
---

For my Professional Networking podcast assignment, I spoke with Pedro Paniago, Offensive Security Manager at PwC Belgium, bug hunter, and a distinct voice in Belgium's security scene.

The conversation started with Pedro's path into hacking, but the main topic became the direction bug bounty is moving in now that AI is part of the workflow. One point that stayed with me is that the old split between broad automation and deep manual testing is becoming weaker. In the past, hunters often had to choose between scanning widely for low-hanging fruit or spending a lot of time going deep on one target. Pedro's view is that AI changes that balance. A good researcher can now go broad and deep, because the model can help correlate more information, summarize flows, and keep more context in play.

We also talked about why this makes bug bounty harder. If everyone has access to stronger models, the easy findings disappear faster. Companies will receive more reports, common issues will be patched earlier, and the competition shifts toward speed, validation, and having a better system around the model. The future is less about asking an AI to "find bugs" and more about building a workflow that helps it reason over real target data.

That led into the hackbot discussion. Pedro broke the system down into layers, and this was one of the most useful parts of the episode for me.

1. **Scaffold.** This is the guidance around the bot: how it should behave, what kind of work it should prioritize, how it should reason through a target, and what boundaries it should respect. A raw model can answer questions, but a scaffold turns it into something closer to a repeatable workflow. It stops the bot from jumping randomly between ideas and gives it a structure for moving from observation to hypothesis to test.

2. **Tooling and recon.** Not every task should be done by the model itself. Recon, crawling, endpoint collection, probing services, parsing JavaScript, and basic checks can often be scripted more reliably and cheaply. The model is more useful when it receives organized data from those tools and spends its reasoning on connections, priorities, and possible exploit paths instead of wasting context on mechanical work.

3. **Context and memory.** A useful hackbot needs to remember what has already been tested, what was a dead end, which technologies appeared on the target, which endpoints looked interesting, and which patterns were seen before. Without memory, the system keeps rediscovering the same information. With memory, every hunt adds more context to the next one, and the bot can make better decisions because it is not starting from zero every time.

4. **Validation and triage.** Pedro stressed that AI can generate a lot of possible findings, but volume is not the same as value. A system needs checks for false positives, duplicated issues, low-impact reports, missing proof, and findings that look interesting but do not really matter. This layer is what turns noisy model output into something that could actually become a bug bounty report.

5. **Correlation.** This is where the system starts connecting patterns across different targets, technologies, JavaScript files, endpoints, and previous observations. If a certain code pattern, library, workflow, or behaviour was vulnerable somewhere else, the system can use that memory to look for similar situations again. That is the part that makes the hackbot feel less like a chatbot and more like an assistant that is learning from previous work.

The biggest argument for building your own hackbot was control. If you only reuse a tool, you may not know how it gathers data, what it trusts, what it misses, or whether it fits your own hunting style. Building one yourself teaches you how prompts, context, memory, token usage, hallucinations, and validation actually work. It also lets you encode your own niche. That part is important, because in a crowded field the advantage is not only having AI. The advantage is having a system that reflects how you think.

We also covered how AI changes infosec outside bug bounty. Pedro's point was that the whole security ecosystem speeds up. Vulnerability research, exploit development, incident response, code review, and defensive monitoring all move faster when AI is involved. That creates pressure on defenders too. If attackers can reverse new CVEs quickly, security teams cannot rely on slow manual processes forever. They need systems that help them correlate evidence, triage faster, and react while the window still matters.

The learning part of the conversation was probably the most practical for me. AI makes it tempting to skip fundamentals, but Pedro was very direct about that risk. You still need the basics, because otherwise you cannot judge the model's output. For newer people, the danger is becoming dependent before building enough technical intuition. The better approach is to understand the technology at a high level, know what you are trying to build or test, and use AI as an accelerator instead of a replacement for thinking.

His final advice was simple: learn the basics, pick a niche, and invest time into understanding AI systems themselves. Not only prompting, but memory, context, limitations, hallucinations, and how to build workflows around models. That connects strongly with how I want to learn security: keep building technical depth, but also build systems that make the work repeatable.

## Episode link

[Listen on Spotify](https://open.spotify.com/episode/5m2AGVcha0TRrEjxJ8M6UL)
