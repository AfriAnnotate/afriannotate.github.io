---
title: Automatic Speech Recognition (ASR)
---

# Automatic Speech Recognition (ASR)

ASR turns spoken audio into text. It is the most developed speech task for African languages and the gateway to the rest, because transcription is the bridge from a recording to something a machine can read. This page covers what is distinctive about building ASR data. The shared recording, consent, and transcription groundwork is in the [Speech overview](../sections/speech.md), and the general pipeline in the Foundations chapters.

## What the data looks like

ASR learns from audio paired with accurate transcripts. The kind of audio matters: read speech, where people read prepared sentences, is clean and easy to collect but does not match how people actually talk, while spontaneous speech is realistic but harder to record and transcribe. African ASR now has both, and the recent surge in purpose-built corpora is the main reason the task has moved fastest. African Next Voices recorded roughly 9,000 hours of everyday speech across eighteen languages in Kenya, Nigeria, and South Africa ([African Next Voices, 2025](../references.md#african-next-voices)), NaijaVoices added 1,800 hours of Igbo, Hausa, and Yorùbá ([Emezue et al., 2025](../references.md#emezue-2025)), and Google's WAXAL released a large multilingual African speech set for ASR and TTS ([WAXAL, 2026](../references.md#waxal-2026)). Domain- and accent-focused sets fill the gaps: AfriSpeech-200 gathered 200 hours of accented English for clinical and general use across thirteen countries ([Olatunji et al., 2023](../references.md#afrispeech-2023)), Kallaama covers agricultural speech in three Senegalese languages ([Gauthier et al., 2024](../references.md#kallaama-2024)), Zambezi Voice covers four Zambian languages ([Sikasote et al., 2023](../references.md#zambezi-2023)), and Mozilla's Common Voice crowdsources read speech for several African languages. Self-supervised models like AfriHuBERT now let a little labelled data go further by pretraining on raw audio first ([Alabi et al., 2025](../references.md#afrihubert-2025)).

## Distinctive annotation: transcription is the hard part

For ASR the annotation is transcription, and its conventions decide the dataset's quality. Settle them before you start: how to write tone and diacritics, which orthography to follow when a language has more than one, how to mark code-switching into a colonial language, and how to handle disfluencies, false starts, and overlapping speech. These are not edge cases for African languages, they are the norm, and inconsistent transcription quietly teaches the model the wrong spelling of half its vocabulary. Transcribers must be native speakers, and a second-pass review of a sample is worth its cost.

## Evaluation

ASR is scored by error rate against a reference transcript. Word Error Rate (WER) is standard but punishes morphologically rich languages unfairly, since one wrong morpheme can mark a whole word wrong, so report Character Error Rate (CER) alongside it. CER is more forgiving and more informative for the agglutinative and tonal languages common on the continent. As always, a human listen to a sample catches failures, such as a systematically mis-transcribed dialect, that an aggregate error rate hides.
