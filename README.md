# R-LMAG — Retrieval-Augmented LLM Multi-Agent Framework for IEC 62443 Layer-Aware Attack Detection

This repository contains the complete analysis pipeline (`rlmagproject.py`) exported from Google Colab
([notebook](https://colab.research.google.com/drive/1hl6I6ENIiHFpcc3h3cQH6tmBn93DjoJ6)).

## Overview

R-LMAG is a research pipeline for detecting cyber-attacks in IEC 61850 / IEC 62443 compliant
substation networks using the **HAI (Hardware Attack Implant)** dataset. It combines:

1. **Phase 1–2 — Data exploration:** archive validation, selective extraction, dataset discovery,
   label distribution, and descriptive statistics (Tables 1–5, Figures 1–4).
2. **Phase 2 — Layer mapping:** zero-unknown mapping of traffic keys/tags to IEC 62443 zones &
   layers (Conformance, Process, Defense), cross-layer correlation scoring (CLCS), semantic event
   extraction, and co-occurrence analysis (Tables 6–13, Figures 5–9).
3. **Phase 3–4 — R-LMAG architecture:** retrieval-augmented Attacker/Defender agent design,
   final evaluation (AUC-ROC, AUC-PR, DR@FPR=5%, F1) and an ablation study (w/o CLCS,
   w/o Defender, equal fusion).

## Running

The script is designed for Google Colab with Google Drive:

```bash
# In Colab: upload rlmagproject.py, ensure ~/MyDrive/rlmag/archive.zip exists, then run
python rlmagproject.py
```

Requirements: `numpy pandas scikit-learn matplotlib openpyxl pyarrow python-docx tabulate`
(installed automatically by the first magic cell when run in Colab).

Outputs (tables CSV, figures at 600 DPI, `logs/manuscript_summary.json`) are written under the
results directory registered throughout the pipeline.

## Repository structure

```
├── README.md            # project title
└── rlmagproject.py      # full pipeline (~5100 lines, Cells 1–26 + figure-regen Cells A–C)
```
