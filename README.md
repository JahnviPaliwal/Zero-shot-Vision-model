## Open-Vocabulary Object Detection Study

### Overview

This project presents a comparative experimental study between:

* **OWL-ViT** — Open-Vocabulary Vision-Language Transformer
* **YOLOv8** — Real-Time CNN-based Object Detector

The goal is to analyze the trade-offs between:

* Semantic flexibility
* Computational efficiency
* Detection stability
* Prompt sensitivity
* Confidence behavior

---

## Motivation

Traditional detectors (e.g., YOLO) operate on fixed datasets (COCO).
Open-vocabulary models like OWL-ViT allow dynamic text-based queries.

This project investigates:

* How much performance is sacrificed for flexibility?
* How stable are open-vocabulary detections?
* How sensitive are predictions to prompt wording?

---

## Experimental Setup

* Framework: PyTorch
* Hardware: Google Colab GPU
* Resolution: 320×240
* Frame Skip: 5
* Confidence Threshold: 0.25

---

## Performance Results

| Metric             | OWL-ViT  | YOLOv8      |
| ------------------ | -------- | ----------- |
| Avg Inference Time | 0.2268 s | 0.0158 s    |
| FPS                | 4.41     | 63.12       |
| Speed Ratio        | —        | ~14× Faster |

---

## Detection Coverage

YOLOv8 detected 200+ objects across multiple COCO classes:

* potted plant (97)
* person (45)
* vase (31)
* cup (25)
* etc.

OWL-ViT detected:

* "a ceiling light" (1 instance)

---

## Confidence & Statistical Analysis

* Confidence t-test p-value: **0.234**
* No statistically significant difference in confidence means
* However, detection imbalance limits statistical interpretability

---

## Prompt Sensitivity

Minor changes in textual prompts significantly affected OWL-ViT detection frequency, demonstrating:

* Strong semantic flexibility
* High prompt sensitivity
* Instability under wording variation

---

## Key Findings

* YOLOv8 achieves real-time performance (~63 FPS)
* OWL-ViT is ~14× slower
* Open-vocabulary detection introduces computational overhead
* Semantic alignment strongly impacts detection reliability

---

## Conclusion

YOLOv8 is production-ready for real-time systems.
OWL-ViT provides research-level flexibility for open-world detection tasks.

---


---

