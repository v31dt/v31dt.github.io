---
title: "OAuth 2.1 as an Attack Surface"
date: 2026-05-14
draft: false
description: "Short note on why OAuth 2.1, MCP authorization, client metadata, and token exchange flows are interesting bug bounty targets."
tags: ["oauth", "bug-bounty", "web-security", "mcp", "authorization"]
---

OAuth is such a good attack surface because there is simply so much that can go wrong during implementation.

With OAuth 2.1 moving forward, and MCP authorization building on top of it, I think this space is going to get a lot of attention again.

The research angle is not only PKCE becoming mandatory or older flows being removed, but also the new client metadata / CIMD-style flows. When authorization servers start fetching client metadata URLs and resolving fields like `logo_uri` or `jwks_uri`, you get a fresh set of SSRF and trust-boundary issues to look at.

Add PKCE downgrade bugs, weak redirect URI validation, token exchange between agents, and confused deputy scenarios, and OAuth suddenly becomes a very fun target to revisit.

For more insights on this, check out the [Critical Thinking - Bug Bounty Podcast episode on OAuth 2.1](https://www.youtube.com/watch?v=mo9LoNHmDhI&t=784s).
