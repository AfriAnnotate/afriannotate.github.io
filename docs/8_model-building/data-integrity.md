---
title: Data Integrity and Contamination Control
sidebar_position: 2
---

# Data Integrity and Contamination Control

A benchmark only measures what it claims to if the test data is genuinely unseen. Data integrity is the discipline of keeping it that way, and it has become harder and more important in the age of large models trained on everything.

## Prevent train-test leakage

The most basic failure is leakage: the same or near-identical examples appearing in both training and test. It inflates scores and hides real weakness, and it is easy to introduce when deduplication happens after splitting rather than before. Deduplicate first, including near-duplicates, then split, and keep the splits fixed so that no one accidentally trains on the test set later. Watch for subtler leakage too, such as the same speaker or document spanning splits in speech and document tasks, which lets a model recognise the source rather than learn the task.

## Watch for benchmark overlap

A new dataset can quietly overlap with existing ones, sharing source texts or examples, which means evaluating on it no longer tests anything new. Before releasing, check your data against the established benchmarks for the language and report any overlap honestly, so that users know what an evaluation on your set actually demonstrates.

## Guard against LLM contamination

The hardest modern problem is contamination: large language models are trained on enormous web crawls that may already contain your test set, so a model can score well by memorisation rather than ability. For African languages this cuts both ways, since the same scarcity that limits training data also means a public benchmark is more likely to have been swept up wholesale. Where you can, keep a portion of the test set private, note the cut-off date of your data, and treat suspiciously high scores from a large model on a public benchmark with caution. Contamination control is now part of building a credible evaluation, not an afterthought.
