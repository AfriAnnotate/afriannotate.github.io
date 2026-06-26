---
title: Object detection
sidebar_position: 3
---

# Object detection

Object detection goes a step beyond classification: it finds where objects are in an image and draws a labelled box around each one. In African contexts it powers tasks like counting livestock from drone imagery, spotting infrastructure in satellite photos, or locating individual plants in a field.

## What the data looks like

A detection dataset is images annotated with bounding boxes, each box marking the location and class of one object. The annotation is far more laborious than classification, since every object in every image must be boxed, which makes tool choice and clear guidelines matter more. African detection data is dominated by aerial and satellite imagery for agriculture and the environment, where boxes mark fields, buildings, or vehicles, and by wildlife and livestock monitoring. As with classification, images captured in real African conditions, low resolution, oblique angles, dense scenes, are essential, because models trained on clean benchmarks degrade on them.

## Annotation and evaluation

Box annotation needs explicit rules: how tightly to fit the box, how to handle occluded or overlapping objects, how small an object must be to mark, and what to do at the image edge. These rules are where annotators silently diverge, so pin them down and measure agreement on a shared set. Detection is evaluated with mean Average Precision (mAP), which rewards both correct labels and accurate placement, built on Intersection over Union (IoU), the overlap between a predicted box and the true one. Report the IoU threshold you used, since mAP at a loose threshold flatters a model that places boxes sloppily.
