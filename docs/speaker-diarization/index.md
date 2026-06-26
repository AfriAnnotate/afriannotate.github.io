---
title: Speaker Diarization
---

# Speaker Diarization

Speaker diarization answers "who spoke when", segmenting an audio recording by speaker. It is the task that makes multi-speaker audio usable, turning a recording of a conversation, meeting, radio panel, or interview into labelled turns that can be transcribed and analysed per speaker. For African languages it is both useful and under-resourced, and the conditions of real African audio make it harder than the benchmarks suggest.

## What the data looks like

Diarization data is multi-speaker audio annotated with speaker-turn boundaries, marking where each speaker starts and stops and which segments belong to the same person. The natural sources are exactly the kinds of recordings African projects already gather: radio broadcasts, community meetings, focus groups, and interviews. Three conditions make African diarization data distinctive and demanding. Overlapping speech is common in natural conversation and is the hardest case for any diarization system. Code-switching means a single speaker may move between languages mid-conversation, which can confuse models that lean on language cues. And recording conditions are variable, since much community audio is captured on phones in noisy settings rather than in studios. Building robust diarization data means embracing these conditions rather than filtering them out.

## Annotation and evaluation

Annotating diarization is a careful listening-and-marking task: the annotator marks each speaker change in time and assigns a consistent label to each distinct voice across the whole recording. The hard parts are overlapping speech, where two labels apply at once, and deciding whether a brief sound is a new speaker or just noise, so the guidelines must cover both. Standard audio-annotation tools support the timeline segmentation this needs. Diarization is evaluated with the Diarization Error Rate (DER), which combines missed speech, false speech, and speaker-confusion errors into one figure, and the Jaccard Error Rate (JER), which weights every speaker equally regardless of how much they talk. As elsewhere, a human review of a sample catches systematic problems that a single aggregate number cannot.
