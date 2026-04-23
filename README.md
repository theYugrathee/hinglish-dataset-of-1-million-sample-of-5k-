# 🇮🇳 Hinglish Dataset — 1.4 Million Samples
### Industrial-Grade Code-Mixed NLP Dataset | By ScaleIndia AI · Founder: Yug Rathee

![Language](https://img.shields.io/badge/Language-Hinglish%20(Hindi%20%2B%20English)-orange)
![Rows](https://img.shields.io/badge/Full%20Dataset-1.46M%2B%20Rows-blue)
![Teaser](https://img.shields.io/badge/This%20File-5%2C000%20Rows-green)
![Pipeline](https://img.shields.io/badge/Pipeline-v7.0--turbo-yellowgreen)
![Quality](https://img.shields.io/badge/Quality%20Score-97.4%25%20Kept-brightgreen)
![License](https://img.shields.io/badge/License-Research%20%26%20Evaluation%20Only-red)
![Contact](https://img.shields.io/badge/Contact-yugrathee28%40gmail.com-purple)

---

> **This repository contains a 5,000-row teaser sample** from the full 1.46 Million+ Hinglish comment dataset built by **ScaleIndia AI** (Founder: Yug Rathee).
> Provided **strictly for research and evaluation purposes only.**
> Commercial use, redistribution, or production-model training requires **explicit written consent** from ScaleIndia AI.

---

## 📌 What is Hinglish?

**Hinglish** is a naturally spoken blend of Hindi and English — the dominant code-mixed language used by **500 Million+ people** across India's internet. It appears in YouTube comments, WhatsApp chats, Twitter/X posts, and product reviews.

It is one of the **most underrepresented yet commercially valuable** languages for AI training today. Most LLMs and NLP models perform poorly on Hinglish because no large, clean, labeled dataset existed — until now.

---

## 🔷 Full Dataset Overview

| Field | Value |
|---|---|
| **Total Rows (Full)** | 1,466,926 |
| **Teaser Rows (This File)** | 5,000 |
| **Language** | Hinglish (Hindi + English code-mixed) |
| **Source** | YouTube comments (industrial-scale scrape) |
| **Pipeline Version** | v7.0-turbo |
| **Format** | JSON Array / JSONL (UTF-8) |
| **Built By** | ScaleIndia AI — Founder: Yug Rathee |

---

## ⚙️ Full Pipeline Cleaning Report — v7.0-turbo

> The full 1.46M dataset was processed through an industrial-grade cleaning pipeline. Below is the verified pipeline output report.

```
======================================================================
  HINGLISH TURBO CLEANING REPORT  —  v7.0-turbo
  Config hash : 37f130be5a81f15b
  Fast JSON   : orjson
======================================================================
  Runtime     : 43.0 min  (2,582 s)
  Throughput  : 583 rows/s
  Dedup engine: MinHash LSH (full dataset)
======================================================================
```

### 📦 Row Count Summary

| Metric | Count | % |
|---|---|---|
| **Total Input Rows** | 1,506,178 | 100% |
| Skipped (checkpoint) | 0 | — |
| Actually Processed | 1,506,178 | 100% |
| ✅ **KEPT (clean)** | **1,466,926** | **97.4%** |
| 🗑️ **REMOVED (trash)** | **39,252** | **2.6%** |

> **97.4% retention rate** — the input data was already high quality. Only genuinely noisy rows were removed.

### 🗑️ Removal Breakdown

| Category | Removed |
|---|---|
| **SCHEMA** | |
| Invalid schema rows | 0 |
| **NOISE / SPAM** | |
| Emoji-only spam | 0 |
| PII-only rows | 0 |
| Garbage characters | 0 |
| Word repetition spam | 7 |
| Random number spam | 1 |
| Empty / blank | 0 |
| *Subtotal* | *8* |
| **LANGUAGE** | |
| Pure Devanagari Hindi | 0 |
| Pure English | 0 |
| Mostly English (>50%) | 29,670 |
| Broken translation | 1,589 |
| Language spam | 0 |
| *Subtotal* | *31,259* |
| **QUALITY** | |
| Abusive content | 5,778 |
| Low quality score | 0 |
| **DUPLICATES** | |
| Exact duplicates | 2,207 |
| Near duplicates (MinHash LSH) | 0 |
| *Subtotal* | *2,207* |
| **TOTAL REMOVED** | **39,252** |

### 🏷️ Full Dataset Label Quality

| Signal Strength | Count | % |
|---|---|---|
| **Strong signal labels** | 230,241 | 15.7% |
| **Weak signal labels** | 543,611 | 37.1% |
| **Fallback labels** | 693,074 | 47.2% |
| Short text rows (≤5 words, flagged) | 250,791 | 17.1% |

### 📊 Quality Score Histogram (Kept Rows)

```
[0.0–0.1]                    0
[0.1–0.2]                    0
[0.2–0.3]                    0
[0.3–0.4]                    0
[0.4–0.5]                    3
[0.5–0.6]                   96
[0.6–0.7]                2,854
[0.7–0.8] █             63,377
[0.8–0.9] ███           225,940
[0.9–1.0] ████████████ 1,174,656
```

> **80%+ of kept rows score 0.9–1.0 quality** — the dataset is overwhelmingly high-grade text.

---

## 📋 5,000-Row Teaser — Audit Report

> This teaser file (`hinglish_teaser_5k.json`) is a stratified, confidence-biased sample of the full dataset.

### 📝 Text Quality

| Metric | Value |
|---|---|
| Average Word Count | **16.4 words/row** |
| Max Word Count | 229 words |
| Lexical Diversity | **16.10%** (unique/total word ratio) |

### 🏷️ Label Reliability

| Metric | Value |
|---|---|
| Strong Signal Rows | 2,002 **(40.0%)** |
| Average Label Confidence | **0.61 / 1.00** |
| Intent Entropy | **2.31** *(High — max theoretical ~3.17)* |

| Label Method | Count | % | Meaning |
|---|---|---|---|
| `strong_signal` | 2,002 | 40.0% | Multiple strong keyword matches — highly reliable |
| `weak_signal` | 1,330 | 26.6% | At least one signal matched — generally reliable |
| `fallback` | 1,668 | 33.4% | Labeled Neutral by elimination |

### 🎯 Intent Distribution (5k Teaser)

| Intent | Count | % |
|---|---|---|
| Neutral | 1,432 | 28.6% |
| Question | 1,151 | 23.0% |
| Request | 1,127 | 22.5% |
| Appreciation | 984 | 19.7% |
| Criticism | 112 | 2.2% |
| Humor | 96 | 1.9% |
| Complaint | 78 | 1.6% |
| Suggestion | 18 | 0.4% |
| Sarcasm | 2 | 0.04% |
| **Total** | **5,000** | **100%** |

### 😊 Emotion Distribution (5k Teaser)

| Emotion | Count | % |
|---|---|---|
| Neutral | 2,611 | 52.2% |
| Happy | 1,064 | 21.3% |
| Curious | 583 | 11.7% |
| Frustrated | 186 | 3.7% |
| Sad | 179 | 3.6% |
| Humor | 140 | 2.8% |
| Fear | 90 | 1.8% |
| Surprised | 71 | 1.4% |
| Angry | 62 | 1.2% |
| Disgusted | 14 | 0.3% |

### ✅ Teaser Health Checks

| Check | Result |
|---|---|
| No duplicate rows | ✅ Pass |
| IDs sequential 1–5000 | ✅ Pass |
| All 9 intent classes present | ✅ Pass |
| All 10 emotion classes present | ✅ Pass |
| Intent entropy > 2.0 (high diversity) | ✅ Pass — **2.31** |
| Avg confidence > 0.5 | ✅ Pass — **0.61** |
| First rows at peak confidence | ✅ Pass — **1.00** |
| PII scrubbed | ✅ Pass |
| Abusive content filtered | ✅ Pass |

---

## 📐 Data Schema

Every row follows this exact structure:

```json
{
    "id": 1,
    "text": "Yaar ye video bahut zyada helpful thi, seriously thank you so much!",
    "intent": "Appreciation",
    "emotion": "Happy",
    "toxicity": "Low",
    "sarcasm": "No",
    "language": "hinglish",
    "quality_score": 0.82,
    "label_confidence": 0.9,
    "label_method": "strong_signal",
    "is_short": false
}
```

| Field | Type | Description |
|---|---|---|
| `id` | Integer | Unique sequential row ID |
| `text` | String | Cleaned, PII-scrubbed Hinglish text |
| `intent` | String | One of 9 intent classes |
| `emotion` | String | One of 10 emotion classes |
| `toxicity` | String | `Low` / `Medium` / `High` |
| `sarcasm` | String | `Yes` / `No` |
| `language` | String | Always `"hinglish"` |
| `quality_score` | Float | Heuristic text quality score (0.0–1.0) |
| `label_confidence` | Float | Labeling confidence score (0.0–1.0) |
| `label_method` | String | `strong_signal` / `weak_signal` / `fallback` |
| `is_short` | Boolean | `true` if fewer than 6 training-grade words |

---

## 🔬 How This Dataset Was Built

1. **Scraping** — YouTube comments collected via industrial async scraper at scale
2. **Normalization** — Unicode normalization, emoji handling, encoding fixes
3. **PII Scrubbing** — Phone numbers, emails, handle names removed
4. **Noise Filtering** — Emoji-only, word repetition spam, garbage chars removed
5. **Language Filtering** — Pure Hindi, pure English, broken translations excluded
6. **Quality Scoring** — Heuristic scoring on lexical richness, structure, length
7. **Deduplication** — Exact SHA-256 + near-duplicate MinHash LSH (128 permutations)
8. **Labeling** — Mega-Regex heuristic labeler across 9 intent + 10 emotion classes
9. **Confidence Scoring** — Every row assigned `label_confidence` (0.0–1.0)

---

## 💼 Ideal Use Cases

- 🤖 **Conversational AI & Chatbot fine-tuning** — intent + emotion labels ready to use
- 🧠 **Sentiment & emotion analysis** in code-mixed Hinglish
- 📚 **Low-resource NLP research** — one of the largest labeled Hinglish datasets publicly available
- 🔍 **Sarcasm & toxicity classification** benchmarks
- 🏗️ **Pre-training or fine-tuning** multilingual / code-mixed LLMs
- 📊 **Academic research** on South Asian internet language

---

## ⚖️ License & Legal

```
Copyright © 2026 ScaleIndia AI — Yug Rathee. All Rights Reserved.

This dataset is provided STRICTLY for research and evaluation purposes only.

PERMITTED:
  ✅ Viewing and evaluating dataset quality
  ✅ Academic and non-commercial research with attribution
  ✅ Sharing with proper credit to ScaleIndia AI (Yug Rathee)

STRICTLY PROHIBITED WITHOUT EXPLICIT WRITTEN CONSENT:
  ❌ Commercial use of any kind
  ❌ Redistribution, re-uploading, or mirroring this data
  ❌ Training production-grade or commercial AI/ML models
  ❌ Selling, licensing, or sublicensing to third parties
  ❌ Claiming ownership or authorship of this dataset

Violation of these terms may result in legal action under applicable
copyright and intellectual property law.
```

---

## 💰 Purchase the Full Dataset

The **full 1,466,926-row Hinglish dataset** is available for commercial licensing.

**What you get with the full dataset:**
- ✅ 1,466,926 cleaned, labeled, deduplicated rows
- ✅ 9 intent classes + 10 emotion classes on every row
- ✅ Toxicity & sarcasm flags
- ✅ Quality score + label confidence score
- ✅ JSON or JSONL format (your choice)
- ✅ Commercial training rights (terms apply)
- ✅ Support for dataset integration queries

### 📬 Contact ScaleIndia AI

| Platform | Contact |
|---|---|
| **Email** | [yugrathee28@gmail.com](mailto:yugrathee28@gmail.com) |
| **Instagram** | [@yugrathee.xe](https://instagram.com/yugrathee.xe) |

> For enterprise licensing, custom dataset slices, or bulk purchases — **email with your use case and company name** for a quote.

---

*Built with ❤️ by Yug Rathee — ScaleIndia AI — April 2026*
