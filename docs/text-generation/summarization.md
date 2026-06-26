---
title: Summarization
sidebar_position: 3
---

# Summarization

Summarization condenses a longer text into a shorter one that preserves its meaning. It comes in two forms. Extractive summarization selects the most important sentences from the source, while abstractive summarization rewrites the content in new words, which is harder and more useful but also more prone to error. For African languages summarization is valuable because it makes long documents in health, news, and government accessible quickly, and it is difficult for the same reason all generation is: scarce training data and morphologically rich languages that defeat simple methods.

## What the data looks like

Summarization needs documents paired with reference summaries. The most widely used multilingual resource is XL-Sum, built from BBC articles and their professionally written summaries, which covers a number of African languages including Amharic, Hausa, Igbo, Kirundi, Oromo, Nigerian Pidgin, Somali, Swahili, Tigrinya, and Yorùbá ([Hasan et al., 2021](../references.md#xlsum-2021)). Beyond it, summarization data for African languages is sparse, so most projects create their own by pairing source documents with summaries written by native speakers. The same care applies as in machine translation: prefer document-level material from a domain that matters, and watch for source documents that are themselves machine-translated.

## Distinctive challenges

The central risk in summarization is faithfulness. An abstractive summary that reads well but states something the source did not is worse than no summary at all, and that risk is higher in low-resource languages where the model's grip on meaning is weaker. Extractive methods avoid invention but can be clumsy in morphologically rich languages where sentence boundaries and salience are harder to detect. Whichever form you target, a human check for whether the summary is faithful to the source is essential.

## Evaluation

The standard automatic metric, ROUGE, measures the overlap of words and short sequences between the generated summary and a reference. It is convenient but unreliable for African languages, because morphological richness means a correct summary can use different surface forms and still be marked wrong, the same weakness that affects BLEU in translation. Embedding-based metrics such as BERTScore capture meaning better, and a dedicated faithfulness or factuality check, whether automatic or human, catches the inventions that overlap metrics miss. As everywhere in generation, native-speaker human evaluation remains the ground truth.
