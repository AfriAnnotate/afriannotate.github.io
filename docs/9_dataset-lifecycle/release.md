---
title: Release Checklist
sidebar_position: 1
---

# Release Checklist

Releasing a dataset is the moment the work becomes useful to others, and a clear checklist is the difference between a resource people can trust and a folder of files they cannot. Run through these before you publish. Each item links to the chapter that covers it in depth.

## Before you release

- **Data cleaned and validated.** Noise removed, duplicates dropped before splitting, language and format checked (see [Data Quality](../4_data-quality/index.md)).
- **Annotation quality verified.** Inter-annotator agreement measured and reported, gold checks passed, disagreement understood rather than hidden (see [Data Quality](../4_data-quality/index.md) and [Annotation Design](../3_annotation-design/workflow-adjudication.md)).
- **Documentation completed.** A datasheet describing what the data is, how it was collected, from whom, and its known limitations (see [Documentation](../6_documentation/documentation.md)).
- **Licensing defined.** A clear licence chosen on purpose, applied to the data, with attribution and provenance recorded (see [Data Governance](../data-governance/index.md)).
- **Ethical review conducted.** Consent confirmed, personal and sensitive data handled, harms considered, community authority respected (see [Data Governance](../data-governance/index.md)).
- **Baselines and splits provided.** Official train, development, and test splits, and at least baseline results, so others can compare fairly (see [Evaluation](../8_model-building/starter-kit.md)).
- **Public access ensured.** Hosted where the community can find it, such as Hugging Face, Zenodo, or the Lanfrica catalogue, with a stable identifier.

A dataset that ticks every box is one the world can find, trust, reuse, and build on, which is the whole point of building it.
