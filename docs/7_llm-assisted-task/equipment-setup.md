---
title: Synthetic Data Creation
sidebar_position: 2
---

# Synthetic Data Creation

Synthetic data is text or labels generated rather than collected, and it is a tempting answer to African data scarcity. It can genuinely help, but it is also where scarcity bites hardest, because generating good synthetic data in a language needs a model that is already good at that language, which is the thing you do not have.

## The methods, from safest to riskiest

The approaches form a spectrum. Data augmentation makes new examples from real ones through paraphrasing or back-translation, and because it stays anchored to real data it is the safest, though back-translation depends on a translation model that may itself be weak. Fully synthetic generation, where an LLM writes new examples from scratch, is the most scalable and the most dangerous, since the model's weaknesses in the language are copied straight into the data. Scenario-based generation, producing data for specific situations a real corpus underrepresents, sits in between. A rigorous evaluation of these strategies for low-resource languages found that careful combinations, such as showing the model real target-language examples and then having it revise its own output, can narrow the gap to real data to as little as five percent, but also that naive synthetic generation often fails for the lowest-resource languages ([LLM Data Generation, 2025](../references.md#llm-datagen-2025)).

## Validate, or do not ship

Synthetic data is only safe if you check it against reality. Validate generated data against the distribution of real data, in vocabulary, length, and label balance, and have native speakers evaluate a sample for fluency and correctness before any of it trains a model. Watch in particular for the contamination that synthetic data spreads, because training on machine-translated or model-generated text degrades the next model and is hard to detect later, the same trap the web-crawl audit exposed in mined data ([Kreutzer et al., 2022](../references.md#kreutzer-2022)). Treat synthetic data as a supplement to real, human-made data for African languages, never as a replacement for it.
