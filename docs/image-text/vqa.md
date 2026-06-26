---
title: Visual question answering
sidebar_position: 2
---

# Visual question answering

Visual question answering (VQA) asks a model a question in natural language about an image and expects an answer: what colour is the car, how many people are there, what is the person doing. For African languages it is a demanding test, because the model must understand both the image and a question posed in a low-resource language at the same time.

## What the data looks like

A VQA dataset is images, questions about them, and answers, usually many questions per image. The first substantial African resource, HaVQA, built Hausa VQA by carefully translating 6,022 English question-answer pairs over 1,555 Visual Genome images, keeping the translations faithful to what the images show ([HaVQA, 2023](../references.md#havqa-2023)). That translation route is the pragmatic starting point, but it has a ceiling: the images and questions come from a Western dataset, so they reflect Western scenes and assumptions. Collecting questions written natively by speakers about images from their own context is harder, but it produces data that actually fits the users, and cultural multimodal benchmarks such as Afri-MCQA push in that direction.

## Annotation and evaluation

VQA annotation is writing questions and marking correct answers, or translating and verifying them against the image, which native speakers must do, since a translated question that no longer matches the picture is worse than useless. Define how to handle open-ended answers, synonyms, and inflected forms before starting. VQA is scored by answer accuracy, often with a VQA score that gives credit when an answer matches several human responses, and the same morphology caveats apply as in text question answering, so a human check on a sample is needed alongside the automatic number.
