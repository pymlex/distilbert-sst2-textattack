# Adversarial examples for DistilBERT with TextAttack

## Overview

It's a TextAttack pipeline for BERT-like binary classification models.

## Dataset

The dataset is GLUE SST-2, which is a binary sentiment benchmark: `0 = negative`, `1 = positive`.

## Attack setup

We attack a small balanced subset of examples that the model `distilbert-base-uncased-finetuned-sst-2-english` already classifies correctly and use `TextFoolerJin2019` to generate adversarial examples.

## Evaluation metrics for 10 adv-examples

| Dataset / Metric | Accuracy | Precision | Recall | F1 |
|---|---:|---:|---:|---:|
| **Clean** | 1.00 | 1.00 | 1.00 | 1.00 |
| **Adversarial** | 0.10 | 0.00 | 0.00 | 0.00 |

## Outputs

* `sst2_textattack_results.csv` includes 10 examples
* `sst2_textattack_summary.csv` includes metrics

## About

DistilBERT for sentiment analysis and TextAttack.
