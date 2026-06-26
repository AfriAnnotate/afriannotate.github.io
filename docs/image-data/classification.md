---
title: Image classification
sidebar_position: 2
---

# Image classification

Image classification assigns a label, or several, to a whole image: this leaf has this disease, this land parcel is this crop, this scan is normal or not. It is the simplest vision task and often the most immediately useful in African settings, where a phone photograph and a classifier can put expert-level screening in a farmer's or a health worker's hands.

## What the data looks like

A classification dataset is images paired with labels. For African work the images usually need collecting rather than scraping, because the relevant subjects, a specific local crop disease, a regional skin condition, a particular landscape, are under-represented in existing datasets. Single-label classification gives each image one category, while multi-label allows several, which fits messy real-world photos better. The defining challenge is domain shift: a classifier trained on clean foreign images fails on photos taken on cheap phones in African field conditions, with poor lighting, cluttered backgrounds, and unfamiliar varieties. The data therefore has to be collected under the conditions the model will actually face.

## Annotation and evaluation

Labelling is choosing the category, and it is only as good as the expertise behind it: a crop-disease label needs an agronomist, a medical label a clinician, and local knowledge throughout. Write clear definitions with example images for each class, use several annotators on a shared sample to measure agreement, and watch class balance, since rare diseases or land types are often exactly the ones that matter and the ones with fewest examples. Evaluation uses accuracy, but on imbalanced data report per-class F1 and, for many-class problems, top-k accuracy, so that strong performance on common classes does not hide failure on rare ones.
