# DL Spring 2026 Kaggle Contest — Text-to-SVG Generation

This repository contains our training and inference code for the NYU Tandon Deep Learning Spring 2026 Kaggle competition on text-to-SVG generation.

## Files

- `TRAINER.ipynb` — LoRA fine-tuning notebook for the Qwen2.5-Coder model
- `INFERENCE.ipynb` — inference notebook used to generate final CSV submissions
- `requirements.txt` — Python package requirements

## Approach

We fine-tuned a Qwen2.5-Coder 3B model using LoRA on the provided training dataset only.  
The task is to generate valid SVG strings from text prompts under the competition constraints.

## Competition Constraints Followed

- No external datasets used
- SVG output formatted as `id,svg`
- Valid SVG generation with sanitization and validation checks
- Reproducible training and inference pipeline
- Fixed random seed

## Training Summary

- Base model: `unsloth/Qwen2.5-Coder-3B-Instruct-bnb-4bit`
- LoRA fine-tuning
- 4-bit loading
- QKV + O + MLP target modules
- Fixed seed
- Cleaned and filtered training SVGs

## Inference Summary

- Batched inference
- SVG extraction + sanitization
- Final submission written as CSV with columns `id` and `svg`

## Reproducibility

Install dependencies and Dataset:

Dataset link: https://drive.google.com/drive/folders/1SZUtg9NFyaZJ75GiVVLelec6GwanKMqa?usp=sharing

```bash
pip install -r requirements.txt
