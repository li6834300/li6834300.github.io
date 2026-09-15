---
layout: blog_post
title: "The Highest-Scoring Way Not to Read"
author: Zhien Li
category: blog
lang: en
tags:
  - reading comprehension
  - assessment
  - second language learning
  - primary education
  - learning analytics
---

There is a way to answer reading comprehension questions that requires no reading. You scan the passage, you scan the options, and you pick the option whose words you have just seen. It is fast, it is cheap, and for the first few years of school it is nearly correct. I find this genuinely funny, in the way that things are funny when they are also slightly horrifying: we spend enormous effort designing instruments to measure understanding, and a child can walk straight past the instrument using a trick that has nothing to do with understanding at all, and be rewarded for it, repeatedly, for years.

---

![Abstract flat illustration: lines of text represented as grey bars, with one identical bar highlighted in two separate columns and joined by a line, while a differently shaped bar stands alone and unconnected, purple and white palette, no text](/images/2026-09-15-matching-words-is-not-reading.png)

## Why the trick works, and then stops working

Early comprehension questions ask what the text said. Under that regime, word-overlap is not a shortcut to the answer — it *is* the answer, or close enough to it that the difference never shows up in a score. The strategy therefore produces no error signal whatsoever during the period in which it is being learned. It gets reinforced by success.

Somewhere around the middle years of primary school, roughly ages eight to ten, the questions change. They stop asking about things *in* the text and start asking about things *concerning* the text: who wrote this, who is it addressed to, what kind of text is it, what is it trying to make you do. Alongside these arrive paraphrase and sequencing items, where the correct answer restates the text in other words.

Notice what this does to the geometry of the problem. In a metatextual or paraphrase item, the correct option is *by design* not lexically present in the passage, and the distractors *by design* are. A plausible wrong answer is built by taking a real phrase from another part of the text and hanging it under the wrong question. So the same heuristic that produced near-perfect scores is now a device that selects wrong answers with better-than-chance reliability. It has not degraded. It has inverted.

The failure looks exactly like a comprehension problem. It is not one. It is a strategy problem wearing a comprehension problem's clothes.

## Three reasons it clusters in second-language readers

First, word-matching has the lowest vocabulary requirement of any available strategy. You do not need to know that *sorting* and *putting like things together* denote the same act; you only need to recognise a shape. For a child whose vocabulary depth trails their peers, this is the cheapest viable solution to the task, which is precisely why it gets used until it is automatic.

Second, decoding fluency improves fast and hides everything behind it. When the technical reading measures climb — and they do climb, often impressively — the adults in the room file reading under *solved*. Nothing in the reporting measures strategy, so nothing contradicts them.

Third, the vocabulary of the new question types is itself subject-specific language. *Genre. Author. Purpose. Instructional text.* These words live in classrooms, not in kitchens. A child who is conversationally fluent can lose marks here and look as though they cannot think, when what they actually have is a gap in a word list nobody wrote down.

## Distinguishing it from its neighbours

Two rival explanations produce the same low score, and the three are separable by the *shape* of the errors rather than their number.

If the problem were decoding, errors would rise with passage length and unfamiliar-word density, and would not care what type of question was being asked. Technical reading measures settle this one, and if those measures sit in a high band the hypothesis can be dropped without further experiment.

If the problem were carelessness, errors would be scattered, and — this is the useful part — they would *move* when the same set is attempted again. Hand a child the same items a few days later. If the same items come back wrong with the same options selected, you are not looking at carelessness. You are looking at a stable decision procedure being faithfully re-executed.

If the problem is word-matching, the errors concentrate in metatextual and paraphrase items, and every wrong option chosen will turn out to be lexically present in the passage.

The third row requires item-level data on *which wrong answer was chosen*. Accuracy alone cannot get you there. A platform that reports only percentages is structurally incapable of supporting this diagnosis: it can tell you a skill is weak and never which wrong idea is holding steady underneath it. When choosing learning software, I would weight per-item error visibility above adaptive difficulty and far above gamification, and I am aware this is not how anyone's procurement checklist is ordered.

One adjacent trap, since it costs so little to mention. If the same report shows full marks in some other subject, the comparison practically writes itself: strong there, weak here. But a perfect score means the instrument has stopped measuring — the difficulty band has no headroom left — and it therefore supports no comparison at all. Read a ceiling as a strength and you will move resources toward the side that was already saturated.

## The intervention is small, and it is not "read more"

Adding reading volume does nothing to a faulty heuristic. Volume gives the heuristic more opportunities to succeed, which is the opposite of what is wanted. Two things need to move instead.

One is the act of going back to the text. The minimal version is a single question, asked while pointing at the option the child chose: *who does this in the story?* No correcting, no explaining, no evaluation. The child goes and finds the sentence. The point is not the answer; the point is that an invisible decision procedure becomes visible — you get to see whether they return to the page or answer from impression.

The other is explicitly teaching the metatextual words, once, on purpose. Native-speaking children absorb them incidentally from classroom talk, which is why they appear on no vocabulary list and get taught to no one.

Text selection helps more than it should. Procedural and expository texts — steps, order, instructions — naturally generate sequencing and paraphrase questions. Advertisements naturally generate *who wrote this and what do they want from you*. Narrative, as it happens, is the genre in which word-matching is least likely to be caught, which may explain why it survives so long.

If the account is right, it makes a checkable prediction: raise the difficulty and accuracy should fall while the error type distribution stays put. If the errors instead scatter across passage length, go back and re-examine decoding. And with no additional practice at all — adding only the return-to-the-text question — paraphrase items should improve before metatextual ones, because one of those needs a single habit and the other also needs the words.
