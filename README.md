# CIFAR-10 Image Classification using CNN

A deep learning project focused on improving image classification performance on the **CIFAR-10 dataset** through various CNN architecture, regularization, data augmentation, hyperparameter tuning, and transfer learning with ResNet-18.

## Overview

The project uses 50,000 labeled CIFAR-10 images, split into **40,000 training images and 10,000 validation images**. Each image is a 32 × 32 RGB image belonging to one of 10 classes.

The goal is to compare different modeling techniques and understand their impact on classification accuracy and overfitting.

## Models & Experiments

- **Baseline CNN:** Established initial performance using convolutional and pooling layers.
- **Regularization:** Applied batch normalization, dropout, weight decay, and early stopping to reduce overfitting.
- **Architecture Optimization:** Experimented with pooling layers, classifier complexity, and additional convolutional layers.
- **Hyperparameter Tuning:** Used Optuna to optimize learning rate, weight decay, dropout rate, and classifier size.
- **Data Augmentation:** Applied image transformations to improve generalization.
- **Deep CNN:** Increased model capacity to learn more complex visual features.
- **Transfer Learning:** Fine-tuned ImageNet-pretrained ResNet-18, using different learning rates for the feature extractor and classifier.
- **Error Analysis:** Examined class-wise performance and error patterns

## Results

The following table summarizes validation accuracy across the major experiments.

| Model / Experiment | Validation Accuracy |
|---|---:|
| Baseline CNN | 69.52% |
| with regularization | 73.89% |
| with additional convolutional layers | 77.66% |
| with data augmentation | 79.67% |
| Deep CNN with data augmentation | 89.15% |
| ResNet-18 with frozen feature extractor | 87.83% |
| ResNet-18 fine-tuned full on 40,000 images with augmentation | **93.81%** |

**Best result: 93.81% validation accuracy**, achieved by fine-tuning ResNet-18 with data augmentation on the full training dataset.

Notably, fine-tuning ResNet-18 with only 2,000 training images achieved approximately 85% validation accuracy, demonstrating the potential of transfer learning when training data is limited.

## Key Findings

- Regularization reduced overfitting and improved generalization.
- Data augmentation significantly improved validation performance.
- Increasing CNN depth helped capture more complex image patterns.
- Fine-tuning a pretrained ResNet-18 outperformed the custom CNN architectures.
- Cats and dogs were among the most challenging classes to distinguish

## Tech Stack

- **Language:** Python
- **Deep Learning framework:** PyTorch
- **Dataset:** CIFAR-10 (CSV-formatted dataset)
- **Hyperparameter Optimization:** Optuna
- **Model:** Convolutional Neural Networks (CNNs), ResNet-18
- **Training Environment:** Kaggle Notebooks and Google Colab


## Acknowledgements

Thanks to Kaggle and Google Colab for providing GPU computing resources, and to the PyTorch community for its open-source deep learning framework.