---
title: "The 5 Levels of Infrastructure as Code"
date: 2026-04-28
draft: false
description: "Reflection on a Howest Tech&Meet about Infrastructure as Code maturity, Azure Bicep, and moving from manual cloud work to governed automation."
tags: ["tech-and-meet", "infrastructure-as-code", "azure", "bicep", "cloud"]
---

![The 5 Levels of Infrastructure as Code proof of attendance](/images/events/five-levels-of-infrastructure-as-code.jpg)

On 28 April 2026, I attended the Howest Tech&Meet **"The 5 Levels of Infrastructure as Code"** at Howest Campus Brugge Station. The session was given by Tim Van Roosbroeck and Dimitry Decan from Orbid, and focused on how organisations move from manual cloud configuration toward mature, governed Infrastructure as Code.

I wanted to attend this talk because infrastructure is one of the areas where mistakes can become expensive very quickly. In security, it is easy to focus on application bugs or malware, but badly managed infrastructure can create just as much risk. Misconfigured access, forgotten resources, inconsistent environments, and manual changes are all problems that attackers can benefit from.

The maturity model made the topic easier to reason about. The first level is basically manual work: clicking through portals, changing settings by hand, and trying to remember what was done. That might work for a small demo, but it does not scale. As the levels progress, infrastructure becomes more repeatable, modular, reviewed, and governed. That is where IaC becomes more than convenience. It becomes a way to reduce drift and make infrastructure changes visible.

The Azure Bicep part was useful because it showed IaC in a concrete ecosystem. I have seen infrastructure automation before, but this session made the structure clearer: templates, modules, parameters, reusable components, and policy-driven deployments. It also showed why cloud work needs discipline. Automation can make good practices repeatable, but it can also repeat bad decisions faster if the design is weak.

For cybersecurity, the main takeaway was that infrastructure should be treated as code because it creates the same need for review, versioning, testing, and ownership. A cloud environment that only exists as a collection of manual portal changes is hard to audit and hard to trust. If the infrastructure is described in code, security discussions become more concrete.

I would recommend this session to students who want to understand how modern cloud teams work. Even if you are not planning to become a cloud engineer, IaC is worth understanding because security, development, and operations all meet there.

Proof and reference:

- [Ticket page](https://eur01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fhowesttech.odoo.com%2Fevent%2F16%2Fmy_tickets%3Fregistration_ids%3D%5B1801%5D%26tickets_hash%3D2ad5168f2cbb6fc2c8f5436e89a33b24e77cf11e066b3196436a5b6ad6c4dcea%26responsive_html%3D1&data=05%7C02%7Crobert.akhmerov%40student.howest.be%7C4abb0daa01c44f74050e08dea45221e6%7C4ded4bb16bff42b3aed76a36a503bf7a%7C1%7C0%7C639128869974463365%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=cyEBOSlVl9GOQxRwwl0JlagUhA0GCkIVcO9QAtyGeIE%3D&reserved=0)
- [Event page](https://howesttech.odoo.com/event/the-5-levels-of-infrastructure-as-code-16/register)
