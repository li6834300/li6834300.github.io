---
layout: blog_post
title: "Three Brushstrokes That Broke the Algorithm"
author: Zhien Li
category: blog
lang: en
tags:
  - AI
  - Cognitive Science
  - Visual Abstraction
  - Research
---

There's a peculiar torture humans have inflicted on machines lately: show an AI a stick figure of a running person drawn by a four-year-old, and ask it *why* those three wobbly lines mean "running." The machine, which can identify a golden retriever from 2,000 pixels with 99.7% confidence, suddenly stammers.

Judy Fan noticed this. And she turned it into a research program.

---

![A minimalist bird sketch faces a geometric neural network — the gap between human intuition and machine reasoning](/images/2026-02-27-where-ai-fails-human-visual-cognition.png)

## The Embarrassing Gap

Fan's lab works on something called visual abstraction — the strange human talent for stripping an object down to its barest semantic bones and still communicating it perfectly. Her benchmark, **SA (Sketch Abstraction)**, quantifies this with a metric called *Portion of Strokes*: the fewer strokes a drawing uses relative to a canonical version, the more abstract it is.

The finding that keeps AI researchers quietly uncomfortable is this: the more abstract a sketch, the worse current vision models perform at *explaining* it — even when they can technically *identify* the object. GPT-4V can tell you "that's a bird." Ask it *why those four lines constitute a bird*, and it produces the verbal equivalent of a shrug dressed in academic language.

This is not a hardware problem. It is a reasoning problem. Specifically, it's a *teleological* reasoning problem — the kind that asks not "what is this?" but "what was this *for*?"

---

## The Two-Second Miracle

A human child drawing a bird doesn't think in pixel distributions. She thinks: *I need to convey flight. A curve for the body. A triangle for the beak. Done.* The drawing encodes *purpose*, not appearance. Each stroke is a decision about *what matters*.

This is what Fan calls the constraint structure of human visual communication. We are exquisitely optimized for high-bandwidth meaning transfer under severe resource constraints — four seconds, three strokes, one piece of paper — because evolution didn't give us a GPU cluster. We got 86 billion neurons and had to be clever.

AI, meanwhile, has the GPU cluster and still can't figure out why a squiggle means "angry."

---

## The Research Moat — And Its Expiration Date

Here's where it gets strategically interesting. Fan's lab is effectively writing an owner's manual for human cognition — documenting precisely where and how humans deviate from what an optimal statistical reasoner would do. This is genuinely valuable research, because AI systems trained on correct-answer distributions can't infer the architecture of human error from first principles.

But this moat has a half-life.

The uncomfortable second-order thought: if AI eventually processes enough *behavioral* data — not just images, but the full trace of human drawing decisions, hesitations, revisions, and errors — it can reconstruct the distribution of human mistakes empirically. At that point, the owner's manual stops being proprietary.

The researchers who survive this transition will be the ones who understand *why* human cognition works the way it does at a mechanistic level, not just that it deviates from the machine's output. Documenting the gap is phase one. Explaining the mechanism is the defensible position.

---

## Why I Find This Personally Unsettling

I spent years building interfaces for humans. Frontend engineering is, at its core, an applied theory of how humans parse visual information under cognitive load. Every design decision I ever made was an implicit claim about what people notice, what they ignore, and why.

Now I'm in education research, which is another domain that runs on the same substrate: understanding how human minds represent, compress, and transfer knowledge.

Fan's work suggests that the most durable research positions lie precisely at this intersection — not "AI does X" or "humans do Y," but the careful, empirical documentation of the gap between them, and eventually, the explanation of that gap.

Three brushstrokes that broke the algorithm. That's the research question worth having.
