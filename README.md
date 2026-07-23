# MRI Style Transfer using CycleGAN

## Overview

This project implements a **CycleGAN-based deep learning framework** for unpaired medical image translation between **T1-weighted** and **T2-weighted** MRI scans.

The objective is to generate realistic MRI images of different contrast levels without requiring paired training data. Such image translation can assist radiologists by providing additional imaging modalities, potentially improving diagnostic accuracy.

This project was completed as part of the **upGrad & IIIT Bangalore PG Diploma in Machine Learning & AI Capstone Project (2021).**

---

## Problem Statement

MRI interpretation often benefits from viewing multiple image contrasts (T1 and T2). However:

- Acquiring multiple MRI sequences increases scanning time.
- Additional scans increase healthcare costs.
- Some patients cannot undergo repeated imaging.

This project uses **CycleGAN** to translate:

- **T1 → T2**
- **T2 → T1**

using an **unpaired dataset**, eliminating the requirement for one-to-one corresponding images.

---

## Dataset

The project uses an **unpaired MRI dataset** consisting of:

- T1-weighted MRI images
- T2-weighted MRI images

> **Note:** The dataset is not included in this repository due to licensing and file size limitations.

Expected dataset structure:

```
dataset/
│
├── trainA/
├── trainB/
├── testA/
└── testB/
```

---

## Project Workflow

### 1. Data Understanding

- Load MRI images
- Build TensorFlow dataset pipeline
- Visualize samples

### 2. Image Processing

- Resize images
- Normalize pixel values
- Data batching
- Data augmentation

### 3. Model Architecture

The project implements a modified CycleGAN consisting of:

- Generator G (T1 → T2)
- Generator F (T2 → T1)
- Discriminator X
- Discriminator Y

Generator architecture:

- Modified U-Net

Discriminator:

- PatchGAN

---

## Loss Functions

The model is trained using:

- Adversarial Loss
- Cycle Consistency Loss
- Identity Loss

---

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Google Colab
- Jupyter Notebook

---

## Repository Structure

```
MRI-Style-Transfer-CycleGAN/
│
├── notebooks/
│   └── MRI_Style_Transfer_CycleGAN.ipynb
│
├── images/
│
├── results/
│
├── models/
│
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
```

---

## Results

The trained CycleGAN successfully learns image translation between:

- T1-weighted MRI
- T2-weighted MRI

Generated images preserve anatomical structures while adapting image contrast characteristics.

Example outputs include:

- Original T1 MRI
- Generated T2 MRI
- Original T2 MRI
- Generated T1 MRI

---

## Future Improvements

- Train on larger MRI datasets
- Improve image resolution
- Quantitative evaluation using SSIM and PSNR
- Deploy using TensorFlow Serving
- Explore diffusion-based medical image translation

---

## Author

**Hanaa Khan**

PG Diploma in Machine Learning & AI

upGrad × IIIT Bangalore

2021

---

## Acknowledgements

- upGrad
- IIIT Bangalore
- TensorFlow
- Keras
