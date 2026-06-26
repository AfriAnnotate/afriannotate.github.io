---
title: Video
sidebar_position: 4
---

# Video

General video understanding covers the tasks that read meaning from ordinary moving images: classifying what a clip shows, detecting actions or events within it, and captioning it in words. For African contexts the uses are practical, from analysing agricultural or health video to making the continent's broadcast and community video searchable.

## What the data looks like

Video data is clips paired with labels, which can be a single class for the whole clip, time-stamped events within it, or a caption describing it. The raw material is plentiful in one sense, since African broadcast, social, and community video is abundant, but labelled African video is scarce, and captioning in particular needs descriptions written in the target language rather than translated from English. The cost and weight of video, large files, slow annotation, and intermittent bandwidth for distributed teams, shape every decision, so most projects work with short clips and a tightly scoped label set rather than long-form video.

## Annotation and evaluation

Video annotation is labelling across time: a whole-clip label is cheap, but marking when actions happen, or captioning, is slow and needs clear rules on event boundaries and on the level of detail a caption should capture. Use tools built for timeline annotation, keep clips short, and measure agreement on a shared set. Evaluation depends on the task: accuracy and F1 for classification, mean Average Precision for temporal detection, and the text-generation metrics from the [Text Generation](../text-generation/index.md) chapter for captioning, where, as with all generation, native-speaker human evaluation is the dependable measure.
