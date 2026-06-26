---
title: Layout & document understanding
sidebar_position: 4
---

# Layout & document understanding

Layout and document understanding recovers the structure of a document, not just its text: which parts are titles, paragraphs, columns, tables, and figures, and how they relate. It is what turns a flat OCR transcript into something usable, and it matters most for the complex documents African digitisation actually deals with, such as multi-column newspapers, government forms, and archival records.

## What the data looks like

A layout dataset is document images annotated with labelled regions, boxes or polygons marking each structural element, and often the reading order and table structure on top. The African challenge is less about script than about source: many target documents are old, scanned unevenly, multi-column, and mix languages and scripts on a single page, which defeats models trained on clean modern business documents. Archival material in particular, with its faded ink, marginalia, and irregular layouts, needs data collected from the real archives rather than borrowed from elsewhere.

## Annotation and evaluation

Annotating layout means drawing and labelling regions, the same skill as object detection but with a document-specific label set, plus marking reading order and table cells where the task needs them. The guidelines must define each region type and how to handle overlap and nesting. Layout analysis is evaluated like detection, with mean Average Precision for how well predicted regions match the true ones and with F1 over structural elements, supported as always by a human check on a sample.
