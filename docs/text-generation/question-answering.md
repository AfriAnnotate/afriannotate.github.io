---
title: Question answering
sidebar_position: 4
---

# Question answering

Question answering returns a correct answer to a question. It takes three main forms. Extractive QA pulls the answer as a span from a given passage, open-retrieval QA first finds the relevant passage and then extracts or generates the answer, and generative QA produces an answer from the model's own knowledge. QA is one of the most useful tasks for African languages, because it turns a pile of documents into something a person can actually ask, and it is also one where current models struggle most.

## What the data looks like

The landmark resource is AfriQA, the first cross-lingual open-retrieval QA dataset focused on African languages, with more than 12,000 questions across ten languages, where the question is asked in the African language and the answer is retrieved from passages that are often in English or French ([Ogundepo et al., 2023](../references.md#afriqa-2023)). That cross-lingual design is itself a response to scarcity, since there is far more reference text in English than in most African languages. Knowledge-style QA is covered by AfriMMLU within the IrokoBench benchmark, which tests multiple-choice knowledge questions across seventeen languages ([Adelani et al., 2024](../references.md#irokobench-2024)). Building new QA data means writing questions and marking correct answers, work that has to be done by people fluent in the language and, for specialised domains, in the subject.

## Distinctive challenges

QA exposes the knowledge gap directly. A model that has read little in a language has little to answer from, and cross-lingual retrieval, while a clever workaround, can lose or distort meaning as it crosses languages. Answer boundaries are also harder to mark consistently in morphologically rich languages, where the same answer appears in different inflected forms. Clear annotation guidelines on what counts as a correct answer span are essential.

## Evaluation

Extractive QA is scored with Exact Match, the fraction of answers that match the reference exactly, and token-level F1, which gives partial credit for overlap. Both inherit the morphology problem: an answer that is correct but inflected differently from the reference can score zero on Exact Match, so F1 and a human check are needed alongside it. For generative QA, where the answer is free text, automatic scoring is even less reliable, and native-speaker human evaluation is the dependable measure.
