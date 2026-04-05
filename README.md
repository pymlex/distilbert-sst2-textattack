# Adversarial examples for DistilBERT with TextAttack

## Overview

It's a TextAttack pipeline for BERT-like binary classification models. It exploits the `TextFoolerJin2019` black-box adversarial attack framework that can fool NLP models by identifying and replacing the most influential words in a text. It utilizes a combination of word importance ranking and synonym substitution based on semantic similarity to generate adversarial examples. This method ensures that the resulting text remains grammatically correct and semantically consistent to human readers while successfully misleading the classifier.

## Dataset

The dataset is GLUE SST-2, which is a binary sentiment benchmark: `0 = negative`, `1 = positive`. It contains 67349 train and
872 validation examples, but we only use the the validation set.

## Attack setup

We attack a small balanced subset of examples that the model `distilbert-base-uncased-finetuned-sst-2-english` already classifies correctly and use `TextFoolerJin2019` to generate adversarial examples.

## Evaluation metrics for 10 adv-examples

| Dataset / Metric | Accuracy | Precision | Recall | F1 |
|---|---:|---:|---:|---:|
| **Clean** | 1.00 | 1.00 | 1.00 | 1.00 |
| **Adversarial** | 0.10 | 0.00 | 0.00 | 0.00 |

## Outputs

* `sst2_textattack_results.csv` includes 10 adversarial examples
* `sst2_textattack_summary.csv` includes metrics
