---
title: Speech-to-Speech Translation
---

# Speech-to-Speech Translation

Speech-to-speech translation (S2ST) takes speech in one language and produces speech in another, the spoken equivalent of a human interpreter. For African languages it is the most ambitious speech task and the least resourced, because it sits on top of three hard tasks at once. This page is short by necessity: dedicated African S2ST data barely exists yet, so the practical advice is about how to assemble it from the pieces you do have.

## Cascaded and direct, and what each needs

There are two ways to build S2ST. A cascaded system chains three components, ASR to transcribe the source speech, machine translation to translate the text, and TTS to speak the result, while a direct system learns to map source speech to target speech in one step. For African languages the cascaded route is almost always the realistic one today, because it can reuse the ASR, MT, and TTS datasets covered elsewhere in this section rather than requiring scarce end-to-end speech-translation pairs. The cost of cascading is that errors compound: a mistake in transcription becomes a mistranslation becomes a wrong word spoken aloud. Direct systems avoid that but need paired source-and-target speech that, for most African language pairs, no one has collected.

## Building the data

If you collect S2ST data directly, the unit is aligned speech across two languages, the same utterance spoken in the source and in the target, with a transcript on each side for training and evaluation. This is expensive, so most projects start cascaded and compose existing resources: an ASR corpus for the source language, a parallel text corpus for the pair (see [Machine Translation](../machine-translation/index.md)), and a TTS corpus for the target. Where you do collect end-to-end data, treat consent and voice rights as you would for TTS, since the target side is synthesised or re-spoken speech.

## Evaluation

S2ST is usually evaluated by transcribing the spoken output and scoring that text against a reference translation, an approach often called ASR-BLEU, with chrF preferred over BLEU for the same morphology reasons as in text translation. Newer speech-aware metrics such as BLASER score the translation directly from the audio. None of these captures whether the output sounds natural and says the right thing, so human evaluation by people fluent in both languages remains essential.
