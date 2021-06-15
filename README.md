# Shopee - Price Match Guarantee 

## Introduction
The aim of this competition is to predict which items are the same products. This is source code/solution to get the Silver Medal in Private LB with score 0.733 of [Shopee - Price Match Guarantee](https://www.kaggle.com/c/shopee-product-matching). 

## Disclaimer

* This is our work, we **DO NOT** represent any organization.
* There's no reproducibility guarantee for notebook which uses GPU and TPU
* Although we use License "The Unlicense", dataset and generated models falls under Shopee Terms and Conditions which can be seen on [Google Docs](https://docs.google.com/document/d/17mWGXdK8kW9wMxiAPWrn_1MnDtCRKxRdiSoz1u5RRDw), [Google Docs (2)](https://docs.google.com/document/d/13-ZxPKqHL0o5CG8YJSHjNe_cJUQnxjctCBRfu_S3sVc/) or [Internet Archive](https://web.archive.org/web/20200704093857/https://docs.google.com/document/d/17mWGXdK8kW9wMxiAPWrn_1MnDtCRKxRdiSoz1u5RRDw/edit)

## Environment List

> Some of the notebook are run on different environment. Use Kaggle TPU on training the model and GPU while submitting the code to get score.

| Environment Name | Description                            |
| ---------------- | -------------------------------------- |
| Kaggle CPU       | 2C/4T CPU, 16GB RAM                    |
| Kaggle GPU       | 2C/4T CPU, 16GB RAM, Nvidia Tesla P100 |
| Kaggle TPU       | 2C/4T CPU, 16GB RAM, TPU v3-8          |

## Notebook description


| Filename           | Link to Kaggle Kernel                                                                      | Environment | Description                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------ | ----------- | ------------------------------------------------------------------------------------------------------- |
| eff3-512.ipynb      | https://www.kaggle.com/mfalfafa/shopee-effb3-512-all-training         | Kaggle TPU  | Create multimodal model with EfficientNet B3 pretrained model and image size 512x512 pixel                                                                 |
| effb5-512.ipynb      | https://www.kaggle.com/mfalfafa/shopee-effb5-512-v2-all-training         | Kaggle TPU  | Create multimodal model with EfficientNet B5 pretrained model using image size 512x512 pixel with MLP                                                             |
| nf-net-f0.ipynb      | https://www.kaggle.com/mfalfafa/shopee-nf-net-all-training         | Kaggle TPU  | Create multimodal model with NFNet-F0 pretrained model using image size 512x512 pixel with MLP                                                             |
| nf-net-f1.ipynb      | https://www.kaggle.com/mfalfafa/shopee-nf-net-f1-all-training  | Kaggle TPU  | Create multimodal model with NFNet-F1 pretrained model using image size 512x512 pixel with MLP                                                            |
| roberta-base-id.ipynb      | https://www.kaggle.com/mfalfafa/shopee-roberta-base-id-all-training  | Kaggle TPU  | Create multimodal model with RoBERTa-Base-Id pretrained model with MLP                                                            |
| tfrecord-512-gen.ipynb      | https://www.kaggle.com/mfalfafa/shopee-tfrecord-512-all         | Kaggle CPU  | Generate TFRecord with image size 512x512 pixel for training Images                                                                              |
| text-cleaner.ipynb      | https://www.kaggle.com/mfalfafa/shopee-text-cleaner-for-roberta-base-id-all         | Kaggle CPU  | Text preprocessing for BERT model                                                                              |
| text-vectorizer.ipynb      | https://www.kaggle.com/mfalfafa/text-vectorizer-for-all-training         | Kaggle CPU  | Generate vectorized text for MLP model                                                                              |

## Dataset

The dataset is available on this repository and/or Kaggle datasets platform.

| Created by         | Directory path                | Link to Kaggle datasets                                                     |
| ------------------ | ----------------------------- | --------------------------------------------------------------------------- |
| Shopee             | `dataset/0_original_csv`      | https://www.kaggle.com/c/student-shopee-code-league-sentiment-analysis/data |
| 01a_ocr.ipynb      | `dataset/1_ocr_text`          | https://www.kaggle.com/ilosvigil/sc-21-ocr                                  |
| 01b_ocr.ipynb      | `dataset/1_ocr_text`          | https://www.kaggle.com/ilosvigil/sc-21-ocr                                  |
| 01c_ocr.ipynb      | `dataset/1_ocr_text`          | https://www.kaggle.com/ilosvigil/sc-21-ocr                                  |
| 01d_ocr.ipynb      | `dataset/1_ocr_text`          | https://www.kaggle.com/ilosvigil/sc-21-ocr                                  |
| 01e_ocr.ipynb      | `dataset/1_ocr_text`          | https://www.kaggle.com/ilosvigil/sc-21-ocr                                  |
| 02a_clean.ipynb    | `dataset/2_with_cleaned_text` | -                                                                           |
| 02b_clean.ipynb    | `dataset/2_with_cleaned_text` | -                                                                           |
| 03_tfidf.ipynb     | `dataset/3_with_tfidf`        | https://www.kaggle.com/ilosvigil/csv-with-cleaned-ocr-text                  |
| 04a_tfrecord.ipynb | -                             | https://www.kaggle.com/ilosvigil/tfrecords                                  |
| 04b_tfrecord.ipynb | -                             | https://www.kaggle.com/ilosvigil/tfrecords-2                                |
| 04c_tfrecord.ipynb | -                             | https://www.kaggle.com/ilosvigil/tfrecords-3                                |

## LB/Leaderboard Score

| Notebook filename | Submission filename    | Used for Final Score | Public LB   | Private LB  |
| ----------------- | ---------------------- | -------------------- | ----------- | ----------- |
| 05a_model.ipynb   | submission.csv         | Yes                  | **0.85325** | **0.84923** |
| 05b_model.ipynb   | submission.csv         | No                   | 0.84085     | 0.84339     |
| 05b_model.ipynb   | submission_tta_0.csv   | Yes                  | 0.84323     | 0.84244     |
| 05b_model.ipynb   | submission_tta_all.csv | No                   | 0.84085     | 0.84339     |

## Reproducibility Guide

> This guide assume you have necessary files (full dataset provided by Shopee) and move it to correct directory path

1. Run `01a_ocr.ipynb`, `01b_ocr.ipynb`, `01c_ocr.ipynb`, `01d_ocr.ipynb` & `01e_ocr.ipynb` on Kaggle Notebook
2. Rename output filename from each notebook

| Notebook Filename | Old filename | New Filename    |
| ----------------- | ------------ | --------------- |
| 01a_ocr.ipynb     | train2a.csv  | train_ocr_1.csv |
| 01b_ocr.ipynb     | train2a.csv  | train_ocr_2.csv |
| 01c_ocr.ipynb     | train2c.csv  | train_ocr_3.csv |
| 01d_ocr.ipynb     | train2d.csv  | train_ocr_4.csv |
| 01e_ocr.ipynb     | test2.csv    | test_ocr.csv    |

3. Run `02a_clean.ipynb` & `02b_clean.ipynb`
4. Run `03_tfidf.ipynb`
5. Run `04a_tfrecord.ipynb`, `04b_tfrecord.ipynb` & `04c_tfrecord.ipynb`
6. Run `05a_model.ipynb` or `05b_model.ipynb`
