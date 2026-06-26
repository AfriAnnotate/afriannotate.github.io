---
title: Annotation Task Design and Human Factors
sidebar_position: 1
---

# Annotation Task Design and Human Factors

The shape of an annotation task decides its quality long before the first label is applied. A task that is clear, well-scoped, and comfortable to do produces consistent data. One that overloads or exhausts the people doing it produces noise, no matter how good the guidelines are. Design the task for the human who will sit with it for hours.

## Estimate task complexity before you scale

Every annotation decision carries a cognitive cost, and that cost compounds over thousands of items. A binary judgment, such as whether a text is offensive or not, is far cheaper than a multi-label one, such as assigning all applicable emotions from a set of eight, which is cheaper again than span-level work like marking every named entity and its type. Estimate the complexity honestly, because it drives both the budget and the error rate. Where a task is genuinely complex, break it into a sequence of simpler decisions rather than asking for everything at once. The Masakhane named-entity effort kept its per-language tasks tractable by giving each language its own small team working to one shared, simple protocol rather than a single sprawling labelling scheme ([Adelani et al., 2022](../references.md#adelani-2022)). Use the pilot to measure the real time per item, and let that number, not optimism, set the schedule.

## Design against annotator fatigue

Quality falls as attention does. Long unbroken sessions, monotonous batches, and ambiguous items all wear annotators down, and tired annotators reach for the easy label rather than the right one. Plan for this with short batches, regular breaks, and rotation across task types where the project allows it. Fatigue is not only a quality problem. For tasks that expose annotators to hate speech, abuse, or other distressing material, which is common in African sentiment and safety datasets, prolonged exposure becomes a wellbeing problem, and it calls for content warnings, the freedom to skip or stop, workload limits, and access to support (covered in the annotation and [data governance](../data-governance/index.md) chapters). Treating annotation as skilled, sustainable work rather than disposable clicks is also what keeps a good team available for the next project ([Sambasivan et al., 2021](../references.md#sambasivan-2021)).

## Let the interface do some of the work

The annotation tool is part of the task design, not a neutral container. A good interface removes whole classes of error before they happen. It constrains inputs to the allowed label set so a typo cannot become a new category, it shows the surrounding context an annotator needs to judge a word inside a sentence, and it uses keyboard shortcuts so the work is fast and the physical strain is low. Two constraints matter especially for African projects. Many annotators work on modest hardware over intermittent, metered connections, so the tool should be light, tolerant of dropped connections, and usable on a small screen. It should also handle the orthography of the target language properly, including diacritics and non-Latin scripts, so that what the annotator types is what gets stored. A task that is awkward to do will be done awkwardly.
