---
layout: post
title: "Whisper AI Platform — Self-Service AI Transcription on Azure"
author: Zhien Li
category: projects
lang: en
ref: whisper-ai-platform
tags:
  - content: Cloud Platform
  - content: AI/ML
  - content: DevOps
preview: projectImg/whisper-ai-platform.svg
align: align-left
urlLinks:
  - url: https://github.com/li6834300/learn_platform_whisper
    name: GitHub Repository
---

I built a **self-service AI transcription platform on Azure** — not to ship a transcription product, but to work through, hands-on, everything an AI platform team is actually responsible for: landing zones, identity, mixed CPU/GPU compute, CI/CD, reusable AI building blocks, governance, and cost control.

## {{page.title}}
-----

The service itself does something simple: turn audio into text, then summarize it and answer questions about it. That simplicity is deliberate. Keeping the application small left room to go deep where a platform team actually lives — in the layer *underneath* the application, where other people's workloads get identity, compute, a paved deployment road, and guardrails they can't accidentally opt out of.

### What it does

* **Transcription with identity-gated tiers.** Small Whisper models run on an always-on CPU node pool. The large model runs on a GPU pool — and access to it is gated by a Microsoft Entra ID app role. Ask for the expensive model without the right role and the API returns `403`, with an explanation of which role you'd need.
* **A GPU pool that scales to zero.** The T4 node only exists while premium work is running. A pending pod wakes it (about five minutes), and it disappears again when idle, so expensive hardware costs nothing at rest.
* **Summarization with versioned prompts.** Prompts live in version-controlled YAML, not in code, and every change is gated in CI by an evaluation suite that checks faithfulness, coverage, length, and structure. A prompt that starts inventing facts fails the build.
* **A RAG building block.** Transcripts are chunked, embedded, and indexed into Azure AI Search; questions are answered strictly from retrieved passages, with citations — and refused when the answer isn't in the transcripts.
* **A demo console.** The API serves a small web UI that makes all of this visible: who you are, which model tiers your roles unlock, whether the GPU node is currently warm or scaled to zero, and the tokens and cost of every AI call.

### How it's built

Everything is infrastructure as code (Bicep): resource group, network, monitoring, Key Vault, container registry, storage, a budget with layered alerts, and an Azure Policy that *denies* untagged resource groups so cost attribution can't erode. Governance is deployed before workloads, not bolted on afterwards.

The part I'm most pleased with is that **there are no secrets anywhere in the system**. GitHub Actions authenticates to Azure through OIDC federation; the Kubernetes pods reach Azure AI Foundry and AI Search through workload identity; the cluster pulls images with its managed identity. Nothing to leak, nothing to rotate. Key-based authentication is switched off at the service level, so it isn't even available as a shortcut.

### What I learned

The interesting problems weren't the ones in the tutorials.

Available quota turned out not to mean an available VM size — the cluster rejected a node type I had quota for, because new subscriptions only get newer SKU generations in that region. Region choice ended up following GPU quota rather than the other way around. My first CI run failed because GitHub now presents OIDC tokens with immutable numeric identifiers in the subject claim, not the documented `repo:owner/repo` form, so the fix was to ask the identity provider what it would actually send instead of assuming. A rolling update deadlocked on a single small node because the default strategy wants room for the old and new pod at once. And a routine deployment nearly woke a billable GPU node, because re-applying the manifests reset its replica count — now it defaults to zero, so automation can never spend money on GPU by accident.

Each of those is a small thing. Together they're the actual texture of platform work: the gap between how a system is documented and how it behaves.

### Stack

Azure · AKS · Bicep · Entra ID · Workload Identity · OIDC federation · GitHub Actions · Docker · Trivy · Azure AI Foundry · Azure AI Search · FastAPI · faster-whisper · OpenTelemetry · Application Insights

*Built as a learning project, with AI assistance, to get hands-on with the full surface of an AI platform engineering role. The Azure resources, identity flows, pipelines, and trade-offs are all real.*
