# Shopee - Price Match Guarantee 


## Introduction

The aim of this competition is to predict which items are the same products. This is source code/solution to get the Silver Medal in [Shopee - Price Match Guarantee](https://www.kaggle.com/c/shopee-product-matching/). 

![Alt text](shopee-pmg-solution.png?raw=true "Shopee - Price Match Guarantee Solution")

## Disclaimer

* This is our work, we **DO NOT** represent any organization
* There's no reproducibility guarantee for notebook which uses GPU and TPU
* Dataset and generated dataset falls under Shopee Terms and Conditions which can be seen on [Kaggle Datasets](https://www.kaggle.com/c/shopee-product-matching/data)


## Environment List

> Some of the notebook are run on different environment. Use Kaggle TPU on training the model and GPU while submitting the code to get public/private score.

| Environment Name | Description                            |
| ---------------- | -------------------------------------- |
| Kaggle CPU       | 2C/4T CPU, 16GB RAM                    |
| Kaggle GPU       | 2C/4T CPU, 16GB RAM, Nvidia Tesla P100 |
| Kaggle TPU       | 2C/4T CPU, 16GB RAM, TPU v3-8          |


## Notebook Description

| Filename           | Link to Kaggle Kernel                                                                      | Environment | Description                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------ | ----------- | ------------------------------------------------------------------------------------------------------- |
| eff3-512.ipynb      | https://www.kaggle.com/mfalfafa/shopee-effb3-512-all-training         | Kaggle TPU  | Create multimodal model with EfficientNet B3 pretrained model and image size 512x512 pixel                                                                 |
| effb5-512.ipynb      | https://www.kaggle.com/mfalfafa/shopee-effb5-512-v2-all-training         | Kaggle TPU  | Create multimodal model with EfficientNet B5 pretrained model using image size 512x512 pixel with MLP                                                             |
| nf-net-f0.ipynb      | https://www.kaggle.com/mfalfafa/shopee-nf-net-all-training         | Kaggle TPU  | Create multimodal model with NFNet-F0 pretrained model using image size 512x512 pixel with MLP                                                             |
| nf-net-f1.ipynb      | https://www.kaggle.com/mfalfafa/shopee-nf-net-f1-all-training  | Kaggle TPU  | Create multimodal model with NFNet-F1 pretrained model using image size 512x512 pixel with MLP                                                            |
| roberta-base-id.ipynb      | https://www.kaggle.com/mfalfafa/shopee-roberta-base-id-all-training  | Kaggle TPU  | Create multimodal model with RoBERTa-Base-Id pretrained model with MLP                                                            |
| tfrecord-512-gen.ipynb      | https://www.kaggle.com/mfalfafa/shopee-tfrecord-512-all         | Kaggle CPU  | Generate TFRecord with image size 512x512 pixel for training of image model Images                                                                              |
| text-cleaner.ipynb      | https://www.kaggle.com/mfalfafa/shopee-text-cleaner-for-roberta-base-id-all         | Kaggle CPU  | Create text preprocessing for BERT model                                                                              |
| text-vectorizer.ipynb      | https://www.kaggle.com/mfalfafa/text-vectorizer-for-all-training         | Kaggle CPU  | Create vectorized text for MLP model                                                                              |
| final-solution.ipynb      | https://www.kaggle.com/mfalfafa/shopee-final-solution         | Kaggle GPU  | Final solution for product predictions. This notebook used for submission                                                                              |


## Generated Models

The models are generated using training notebooks. This models can be used to make quick submission using final-solution notebook.

| Training file         | Generated model                | Link to Kaggle datasets                                                     |
| ------------------ | ----------------------------- | --------------------------------------------------------------------------- |
| effb3-512.ipynb             | `EfficientNet B3 + MLP with ArcMargin`      | https://www.kaggle.com/mfalfafa/shopee-effb3-512 |
| effb5-512.ipynb      | `EfficientNet B5 + MLP with ArcMargin`          | https://www.kaggle.com/mfalfafa/shopee-effb5-512-v2                                  |
| nf-net-f0.ipynb      | `NFNet-F0 + MLP with ArcMargin`          | https://www.kaggle.com/mfalfafa/shopee-nfnet-512                                  |
| nf-net-f1.ipynb      | `NFNet-F1 + MLP with ArcMargin`          | https://www.kaggle.com/mfalfafa/shopee-nfnet-f1-512                                  |
| roberta-base-id.ipynb      | `RoBERTa + MLP with ArcMargin`          | https://www.kaggle.com/mfalfafa/shopee-roberta-base-id                                  |


## Dependency Datasets

Dependency datasets are used for training the model and submitting the solution.

| Dataset name         | Description		| Link to Kaggle datasets                                                     |
| ------------------ | ------------------ | ----------------------------- |
| keras_efficientnet_whl      | Python libraries for Keras EfficientNet model | https://www.kaggle.com/alanchn31/keras-efficientnet-whl   |
| nfnets_keras    | Python libraries for NFNet model | https://www.kaggle.com/dsofen/nfnets-keras |
| tfroberta_base_indonesian    | Pretrained model for RoBERTa-Base-Id | https://www.kaggle.com/mfalfafa/tfroberta-base-indonesian |
| NFNET_Model_Checkpoints_270421    | Pretrained models for NFNet | https://www.kaggle.com/dsofen/nfnet-model-checkpoints-270421 |


## LB/Leaderboard Score

| Notebook filename | Submission filename    | Public LB   | Private LB  |
| ----------------- | ---------------------- | ----------- | ----------- |
| final-solution.ipynb   | submission.csv         | **0.744** | **0.733** |


## Reproducibility Guide

> This guide assume you have necessary files (full dataset provided by Shopee and dependency datasets), move it to correct directory path and run it on Kaggle Notebook.

1. Run `text-vectorizer.ipynb`, `text-cleaner.ipynb`
2. Run `tfrecord-512-gen.ipynb`
3. Run `effb3-512.ipynb`
4. Run `effb5-512.ipynb`
5. Run `nf-net-f0.ipynb`
6. Run `nf-net-f1.ipynb`
7. Run `final-solution.ipynb`
