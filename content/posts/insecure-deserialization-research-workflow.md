---
title: "Insecure Deserialization Research Workflow"
date: 2026-05-16
draft: false
description: "Short note on insecure deserialization research, gadget chain discovery, AI-assisted analysis, and why the workflow transfers across runtimes."
tags: ["deserialization", "php", "android", "ai", "security-research"]
---

Insecure deserialization doesn't get the attention it deserves.

Finding the sink is one thing, but the actual painful part is usually exploitability: building the gadget / POP chain and proving the payload actually works in that specific runtime. That's the part that used to eat most of the researcher time.

I think AI opens up a pretty big opportunity here. Not really as some magic "generate exploit" button, but to automate a lot of the chain discovery process: finding reachable gadgets, killing dead paths, reasoning about object/property constraints, and validating candidates.

I'm currently working on a PHP-targeted system around this, but Android seems like a really interesting vector too. Backup flows, IPC handlers, deep link parsers, all those "internal" surfaces feel like places where this class of bug can hide.

This is also what makes deserialization research interesting to me: the details change between PHP, Java, Android, etc., but the mindset transfers.

You're still tracking the same core thing: where untrusted data becomes objects, what code those objects can trigger, what gadget surface exists in that runtime, and whether you can build a real chain to a meaningful sink.

The payload formats and language quirks are different, but the research workflow is very similar.
