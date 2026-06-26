---
title: Evaluation, Benchmarking, and Starter Kits
sidebar_position: 1
---

# Evaluation, Benchmarking, and Starter Kits

A dataset's worth is shown by how well it lets people measure progress. Evaluation is where a corpus becomes a benchmark, and for African languages it is where the field's real standing becomes visible, since broad benchmarks keep finding a wide gap between English and African languages on most tasks ([AfroBench](../references.md#afrobench)).

## Evaluation that fits the task and the language

Each task has its own metrics, covered in the task chapters: error rates for speech and OCR, chrF over BLEU for translation, F1 for classification, and human evaluation wherever generation is involved. Two principles cut across all of them for African languages. Choose metrics that are fair to rich morphology, since word-level measures like BLEU and WER penalise correct-but-inflected output, which is why character-level measures are preferred. And never let an automatic score stand alone, because native-speaker human evaluation is the only reliable judge of fluency, adequacy, and cultural fit. Report results per language and per class rather than as a single average, so that strong performance on a well-resourced language or a common class cannot hide failure elsewhere.

## Splits, generalization, and bias

How you split the data shapes what the benchmark measures. Make the train, development, and test splits cleanly separated, with no leakage, and consider domain-aware or cross-lingual splits that test whether a model generalises rather than memorises. African evaluation should test the things that actually break in deployment: cross-lingual transfer between related languages, domain shift from clean training data to messy real input, and robustness across dialects and accents. Bias and robustness evaluation belongs here too, checking whether performance holds across the genders, regions, and varieties the data is meant to serve.

## Ship a starter kit

A dataset is far more useful when it comes with a way to use it. Provide baseline models for the task, training and evaluation scripts, and clear reproducibility instructions, so the next person starts from a working result rather than a cold file. Defining the official splits and a leaderboard, or at least published baseline scores, gives the community a shared yardstick and positions the dataset against existing benchmarks such as IrokoBench and AfroBench ([Adelani et al., 2024](../references.md#irokobench-2024); [AfroBench](../references.md#afrobench)). The easier you make it to get a first number, the more people will build on your work.
