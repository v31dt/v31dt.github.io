---
title: "AInalyzer"
date: 2025-09-01
draft: false
description: "An open-source AI-powered Burp Suite extension for iterative security investigation with human oversight."
tags: ["burp-suite", "ai", "security-automation", "open-source"]
---

## Context

![AInalyzer interface](/images/projects/ainalyzer.png)

AInalyzer is an open-source AI-powered Burp Suite extension. It integrates an AI assistant into HTTP endpoint security investigations while keeping a human in the loop.

Project repository: [github.com/v31dt/ainalyzer](https://github.com/v31dt/ainalyzer)

It supports OpenAI-compatible chat completion APIs, local OpenAI-compatible servers such as Ollama or LM Studio, OpenAI directly, and coding agents through AgentAPI. The AgentAPI mode can connect the extension to tools such as Codex, Claude Code, Gemini, Aider, or Goose.

The workflow is built around analyst control. A captured HTTP request/response can be sent to AInalyzer, which generates several follow-up testing tasks. The analyst then executes one proposed step at a time, reviews the generated request, response, AI summary, and task history, and decides whether to continue.

## Technologies

- Burp Suite extension development
- AI-assisted analysis
- HTTP security testing
- Human-in-the-loop workflows
- OpenAI-compatible APIs
- AgentAPI
- Ollama / LM Studio style local model endpoints

## Reflection

AInalyzer reflects my interest in combining AI with practical security work. The main idea is not to replace the tester, but to make investigation faster while keeping human judgement in control.
