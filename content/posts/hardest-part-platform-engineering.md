---
title: "The Hardest Part of Platform Engineering"
date: 2026-06-05T13:06:25-10:00
draft: false
tags: ["platform engineering", "infrastructure", "integration", "trust", "capability cards", "physical AI", "edge devices", "SPIFFE", "Vault", "service meshes", "IAM"]
categories: ["platform engineering", "physical AI", "edge devices", "infrastructure"]
description: "Thinking through the integration problem in platform engineering and how a missing abstraction for trust and capability exchange is holding us back."
showToc: true
TocOpen: false
---

The hardest part of platform engineering isn't the platform.

It's integration.

Connecting two systems means configuring secrets, establishing identities, setting up trust. It's almost always manual work. Often bespoke. The kind of thing that can take an engineer a full day even when they've done it before — because every integration has its own surface area and its own quirks.

We have IaC for systems. We have GitOps for deployments. But for *integrations* — the connective tissue that makes a platform actually work — what do we have?

I've been sitting with this problem from two directions at once: as someone building out platform engineering at Agility Robotics, and as someone designing identity and trust systems for physical AI and edge devices that need to communicate with cloud services, each other, and the humans operating them.

The problems look identical.

We have the atoms. SPIFFE for workload identity. Vault for dynamic secrets. Service meshes for policy. IAM for cloud trust. Real progress, real tooling. But they live in different systems with different schemas — and nobody has composed them into a standard for the *relationship itself*: its purpose, its capabilities, its history, its lifecycle.

The integration is still tribal knowledge. The trust still resets on every handshake.

What if it didn't? What if two systems could exchange a credential that carried not just identity, but a capability manifest and a trust history — like an agent capability card, but for infrastructure? What if trust accumulated over time, grounded in actually-delivered results?

I think its a missing abstraction and that it's not a coincidence that AI agent protocols had to invent capability cards for the same reason platform engineers still manually configure every integration. The composition layer was never built.
