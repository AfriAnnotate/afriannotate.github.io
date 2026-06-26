---
title: Speech Emotion Recognition
---

# Speech Emotion Recognition

Speech emotion recognition (SER) reads emotion from how something is said rather than what is said, from pitch, energy, and rhythm. It is one of the most subjective and culturally variable tasks in the playbook, and dedicated African speech-emotion data is still scarce, which makes how you design the annotation more important than the size of the dataset.

## What the data looks like, and why it is hard

SER data is audio clips labelled with an emotion, either as categories such as anger, joy, or sadness, or along continuous dimensions such as how positive and how aroused the speaker sounds. The shortage of African speech-emotion corpora means most work starts from scratch or borrows from related text-emotion efforts: the BRIGHTER and AfriEmo datasets behind SemEval-2025's emotion task cover emotion in text across more than a dozen African languages and are a useful reference for taxonomy and culture, even though they are text rather than speech ([BRIGHTER, 2025](../references.md#brighter-2025)). The deeper difficulty is that emotional expression is cultural. The vocal cues that read as anger or as respect vary across communities, and an emotion taxonomy built for English speakers may not fit how a given African language and culture expresses feeling. Decide the taxonomy with the community, not for it.

## Annotation: disagreement is part of the signal

Because emotion is subjective, SER is the clearest case for the perspectivist approach from [Annotation Design](../3_annotation-design/workflow-adjudication.md). Several annotators from the relevant community should label each clip, and when they disagree, that disagreement often reflects genuine variation in how people hear emotion rather than error. Recruit annotators across the dialects and backgrounds of the speaker community, record their context where consented, and consider preserving the spread of labels rather than collapsing it to a single emotion. Annotator wellbeing matters here too, since some emotional audio is distressing to label.

## Evaluation

SER is evaluated with accuracy and F1, but because emotion datasets are usually imbalanced, with neutral clips far outnumbering strong emotions, report unweighted (per-class) accuracy alongside weighted accuracy so that good performance on the common classes cannot hide poor performance on the rare ones. Where the data preserves multiple annotators, evaluating against the distribution of human labels is more honest than forcing a single answer.
