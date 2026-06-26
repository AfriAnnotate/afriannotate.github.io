---
title: Segmentation
sidebar_position: 4
---

# Segmentation

Segmentation is the most detailed image task: instead of a box, it labels every pixel, outlining the exact shape of objects or regions. It matters in African work wherever a precise area or boundary is the point, such as measuring the exact extent of a crop field, delineating a lesion in a medical scan, or mapping land cover from satellite imagery.

## What the data looks like

A segmentation dataset pairs images with pixel-level masks. Semantic segmentation labels every pixel by class without separating individual objects, while instance segmentation also tells apart one object from another of the same class. The data is dominated by the same high-value African domains, with crop-field boundary sets like LacunaLabels and land-cover sets like LandCoverNet built because precise African-landscape masks did not exist. Satellite segmentation carries its own difficulty, cloud cover, which leaves gaps that are often filled by combining optical with radar imagery.

## Annotation and evaluation

Pixel-level annotation is the most expensive labelling in this playbook, so design it to be feasible: use tools with smart boundary assistance, define exactly how to treat ambiguous edges and mixed pixels, and pilot to measure how long a mask really takes before committing a budget. Because masks are so detailed, agreement is best measured by overlap rather than exact match. Segmentation is evaluated with mean Intersection over Union (mIoU), and with the Dice coefficient or pixel accuracy, all of which compare predicted masks to reference masks by how much they overlap rather than demanding identical pixels.
