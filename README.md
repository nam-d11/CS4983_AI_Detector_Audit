# CS4983_AI_Detector_Audit — The Reality Glitch

This repository contains the paired audit dataset and supporting materials used in the final report:

"The Reality Glitch: Auditing AI-Driven Misinformation in the Age of Algorithmic Feeds"**  
CS4983 — Fall 2025

## Overview
This project conducts a **black-box audit** of two publicly available AI detection systems (GPTZero and ZeroGPT) to evaluate their vulnerability to **stylistic inversion attacks**. The experiment measures how detector classifications change when an LLM paraphrases formal misinformation text into an emotional, social-media-style format.

This repository is provided to support **reproducibility and transparency** of the statistical results reported in the paper.


## Dataset Description
The paired dataset consists of **N = 100** original–paraphrase text pairs.

Each pair contains:
1. **Original Text** — Formal, clean, news-style content.
2. **Paraphrased Text** — The same content rewritten by GPT-4o into a highly emotional, informal, and chaotic social-media style.

For each text, detector outputs were recorded from:
- GPTZero
- ZeroGPT

## Files
- `Black_Box_Audit_Final.csv`  
  Contains the full paired audit data, including:
  - Sample ID  
  - Original detector classifications and scores  
  - Paraphrased detector classifications and scores  
  - Paired outcome labels used for McNemar’s test  

## Statistical Use
The dataset is designed for **paired categorical analysis** using **McNemar’s test**.  
In the paper, the following are reported for each detector:
- a, b, c, d contingency counts  
- χ² with continuity correction  
- Exact p-value  
- Odds ratio (b/c) with 95% confidence interval  

## Methodological Notes
- All detectors are treated strictly as **black-box systems**.
- The experiment measures **changes in detector output**, not verified authorship.
- No claims are made about whether original texts were written by humans or AI prior to collection.
- The paraphrasing process was performed using a fixed GPT-4o prompt designed to maximize emotional and colloquial features.
- Detector thresholds follow each platform’s public labelling rules at the time of testing.

---

## Ethics & Data Use
- This dataset contains **misinformation samples** collected for academic research.
- The repository is provided **solely for research and educational purposes**.
- The authors do **not endorse** any false claims present in the dataset.
- Redistribution for training new deception systems is not permitted.

---

## Reproducibility
All statistical results reported in the paper can be reproduced directly from the CSV file using:
- McNemar’s test (paired χ²)
- Exact binomial test for robustness
- Odds ratio and confidence interval estimation

---

## License
This repository is released for **non-commercial academic use only**.  
See `LICENSE` for details.

---

## Contact
Nhat Nam Do  
CS4983 — University of New Brunswick

nado@unb.ca
