---
title: "PQC: How to Prepare for the Quantum Era"
date: 2026-03-24
draft: false
description: "Reflection on a Howest Tech&Meet about post-quantum cryptography, quantum readiness, and why organisations need to understand their cryptographic footprint."
tags: ["tech-and-meet", "pqc", "cryptography", "quantum", "cybersecurity"]
---

![PQC: How to Prepare for the Quantum Era proof of attendance](/images/events/pqc-how-to-prepare-for-the-quantum-era.jpg)

On 24 March 2026, I attended the Howest Tech&Meet **"PQC: How to Prepare for the Quantum Era"** at Howest Campus Brugge Station. The speaker was Sarah Ampe, Digital Risk Manager at EY Belgium, who works around cryptography, PKI, and post-quantum readiness. The session focused on what happens when current public-key cryptography becomes vulnerable to quantum computing, and what organisations can already do before that becomes an emergency.

I wanted to attend this talk because cryptography often feels like one of those topics that people respect, but postpone. In offensive security, it is easy to focus on web bugs, mobile apps, malware, or infrastructure misconfigurations because the feedback loop is fast. Post-quantum cryptography is different. The risk is slower, but the impact is huge. If an organisation does not know where it uses cryptography, which systems depend on old algorithms, and how long sensitive data needs to remain confidential, it cannot make a serious migration plan.

The concept that stood out most was **"harvest now, decrypt later"**. That threat model makes PQC feel much more practical. Attackers do not need a mature quantum computer today to create risk. They can collect encrypted traffic or stored data now and wait until decryption becomes realistic later. That is especially relevant for governments, financial institutions, healthcare, and any organisation dealing with long-lived secrets.

The talk also connected well with my interest in threat-centred thinking. PQC is not just a math topic. It is an inventory, architecture, risk, and timing problem. Before a company can migrate, it needs to understand its cryptographic footprint: certificates, protocols, libraries, third-party dependencies, embedded systems, and legacy applications. That kind of mapping is security work that sits between engineering and risk management.

I would recommend this session to cybersecurity students because it shows a side of security that is easy to underestimate. Not every important problem looks like an exploit chain. Some problems are about preparing early enough that the future does not arrive as a production incident.

Proof and reference:

- [Ticket PDF](/files/events/pqc-ticket-robert-akhmerov.pdf)
- [Event page](https://howesttech.odoo.com/event/pqc-how-to-prepare-for-the-quantum-era-17/register)
