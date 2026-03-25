# Prosody-Based Curriculum Learning for ASR

## Project Overview

This project explores the use of **prosody-based curriculum learning** to improve the training of end-to-end Automatic Speech Recognition (ASR) systems.

The goal is to train ASR models using a curriculum learning strategy, where training examples are presented in a meaningful order, starting from easier samples and progressively incorporating more difficult ones.

The project covers:

- Exploratory data analysis  
- Analysis of prosodic features and their relationship with ASR performance  
- Systematic experimentation (training and evaluation)  

---

## Motivation

Curriculum Learning (CL) is a training strategy in which examples are presented in a structured order based on their difficulty. Defining an appropriate **difficulty metric** is a key challenge.

This project investigates whether **prosodic features of speech** (e.g. pitch variation, intensity, voice quality) can be used to define such a metric.

---

## Contributions

- Analysed the relationship between prosodic features and transcription quality (WER) using correlation, regression, and quantile-based binning  
- Identified prosodic features as predictors of transcription difficulty  
- Designed a **prosody-based difficulty metric** for curriculum learning based on this analysis  
- Conducted **systematic experiments** comparing:
  - Baseline training  
  - Curriculum learning  
  - Anti-curriculum strategies  

---

## Methodology

### 1. Feature Analysis

A set of **prosodic features** (pitch, intensity, and voice quality) was analysed against **Word Error Rate (WER)** obtained from a pre-trained ASR system.

The analysis included:

- Correlation analysis  
- Regression  
- Quantile-based binning of feature values  

---

### 2. Difficulty Metric Design

Prosodic features showing a strong relationship with transcription error were used to define a **difficulty metric**.

In particular, **pitch variation (abs(mean_delta_f0))** was selected as a key feature to structure the curriculum.

---

### 3. Curriculum Learning Experiments

Training experiments were conducted comparing:

- **Baseline training** (random order)
- **Curriculum learning** (easy → difficult)
- **Anti-curriculum** (difficult → easy)

---

## Repository Structure

```
.
├── src/                             # Analysis scripts
│   ├── add_num_words.py
│   ├── correlation.py
│   ├── extract_experiments.py
│   └── plot_features.py
│
├── outputs/                         # Analysis outputs (plots, PDFs)
│   ├── prosodic_features_vs_wer.pdf
│   ├── prosodic_features_bins_vs_wer.pdf
│   └── ...
│
├── docs/                            # Thesis and presentation
│   ├── thesis.pdf
│   └── presentation.pdf
│
└── README.md
```

---

## External Framework

Experiments were conducted on Transformer-based end-to-end ASR systems using the **Speacher** framework.

https://github.com/gcambara/speacher

Related contribution:

https://github.com/gcambara/speacher/pull/2

---

## Academic Context

This project was developed as part of the **Master’s Degree in Language Technologies**.

---

## Technologies

- Python  
- Pandas, NumPy, SciPy  
- Matplotlib  
- Praat / Parselmouth  
- SpeechBrain / Fairseq  
