# Denthara

### Lightweight Teeth Segmentation and Natural Whitening from Facial Images

> **Denthra** is a research-oriented, full-stack computer vision system for detecting and precisely segmenting visible teeth from human facial images, followed by an optional natural-looking teeth-whitening pipeline operating exclusively within the predicted teeth regions.

The project is designed around **lightweight, near-real-time inference**, reproducible experimentation, and deployment as a complete web application.

---

## Overview

Denthra combines modern deep-learning-based instance segmentation with classical image-processing techniques to create an end-to-end teeth analysis and whitening pipeline.

Given a facial image, the system aims to:

1. Detect visible teeth.
2. Generate precise pixel-level teeth masks.
3. Exclude lips, gums, tongue, and surrounding facial regions.
4. Avoid false teeth predictions when the mouth is closed.
5. Apply a controlled and adaptive whitening transformation.
6. Preserve natural tooth texture, highlights, shadows, and boundaries.
7. Provide the result through a full-stack web application.

The project will evaluate multiple candidate architectures and configurations before selecting the final model based on a combination of:

* segmentation accuracy
* boundary quality
* false-positive behavior
* closed-mouth robustness
* model size
* inference latency
* computational requirements
* deployment feasibility

---

# 1. Motivation

Teeth whitening applications often rely on simple color manipulation or predefined facial regions. Such approaches can produce unnatural results when the system cannot accurately distinguish teeth from:

* lips
* gums
* tongue
* facial skin
* oral shadows

A reliable whitening system therefore requires a robust localization mechanism before any appearance modification is applied.

Denthara approaches the problem as two sequential tasks:

```text
Facial Image
     │
     ▼
Teeth Segmentation
     │
     ▼
Precise Teeth Mask
     │
     ▼
Mask Refinement
     │
     ▼
Natural Whitening
     │
     ▼
Final Image
```

The segmentation stage is treated as the primary computer vision problem, while whitening is implemented as a controlled downstream image-processing task.