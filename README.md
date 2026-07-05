# Physics-Grounded Self-Supervised Vision (PGSV)

A PyTorch implementation of **Physics-Grounded Self-Supervised Vision (PGSV)**, a novel self-supervised learning framework that integrates **Variational Autoencoders (VAE)**, **Slot Attention**, **Perspective Geometry**, **Temporal Dynamics Prediction**, and **Contrastive Learning** to learn structured and physically consistent visual representations.

This repository contains the complete implementation used for the PGSV proof-of-concept experiments on the **MNIST** dataset.


## Overview

Traditional self-supervised vision models primarily learn appearance-based representations through image reconstruction or feature consistency. PGSV extends this paradigm by incorporating physics-inspired inductive biases that encourage the model to learn:

- Object-centric representations
- Geometric consistency
- Temporal coherence
- Structured latent spaces
- Predictive world modeling

Although demonstrated on MNIST, the framework is designed as a foundation for future research in physics-aware visual intelligence.


## Features

- Variational Autoencoder (VAE) backbone
- Slot Attention for object-centric representation learning
- Perspective geometry module
- Residual temporal dynamics prediction
- NT-Xent contrastive learning
- Multi-objective self-supervised training
- Latent space visualization using t-SNE
- Reconstruction comparison with baseline VAE
- Object discovery and clustering evaluation


## Model Architecture

The PGSV pipeline consists of the following components:

Input Image
↓
CNN Encoder
↓
Latent Distribution (μ, σ)
↓
Reparameterization
↓
Slot Attention
↓
Geometry Module
↓
Temporal Dynamics Predictor
↓
Decoder
↓
Reconstructed Image

Training is performed using a composite loss consisting of:

- Reconstruction Loss
- KL Divergence
- Temporal Consistency Loss
- Latent Prediction Loss
- Geometry Consistency Loss
- NT-Xent Contrastive Loss


## Repository Contents

```
.
├── pgsv-mnist.ipynb        # Complete implementation
├── README.md
└── images/                 
```


## Dataset

The project uses the **MNIST Handwritten Digits** dataset.

Instead of using consecutive video frames, synthetic temporal pairs are created through strong data augmentations including:

- Random Rotation
- Translation
- Scaling
- Gaussian Blur
- Random Erasing

These augmentation pairs simulate temporal observations for self-supervised learning.


## Training

The model is trained using:

- Optimizer: Adam
- Epochs: 40
- Batch Size: 256
- Learning Rate: 1e-3

Composite loss includes:

- Reconstruction Loss
- Temporal Consistency
- Latent Prediction
- Geometry Loss
- Contrastive Loss
- KL Regularization


## Evaluation

The notebook includes:

- Reconstruction comparison
- Latent space visualization (t-SNE)
- Object discovery evaluation
- SSIM
- PSNR
- Adjusted Rand Index (ARI)
- Clustering Accuracy


## Results

Compared to a baseline Variational Autoencoder, PGSV achieved:

| Metric | Baseline VAE | PGSV |
|---------|-------------:|------:|
| Reconstruction MSE | 0.0228 | **0.0159** |
| Relative Improvement | — | **30.3%** |
| Latent Prediction MSE | — | **0.0003** |
| Object Discovery Accuracy | — | **72.19%** |
| ARI | — | **0.5177** |
| SSIM | — | **0.7737** |
| PSNR | — | **19.03 dB** |


## Notebook Structure

The notebook is organized into:

1. Dataset Preparation
2. Model Architecture
3. Slot Attention Module
4. Geometry Module
5. Temporal Dynamics Module
6. Decoder
7. Contrastive Loss
8. PGSV Model
9. Training
10. Evaluation
11. Visualizations
12. Summary


## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Scikit-learn
- Matplotlib

## Future Improvements

- Vision Transformer (ViT) encoder
- Real video datasets
- Graph Neural Networks for physical interactions
- Differentiable physics engines
- Neural Radiance Fields (NeRF)
- Multi-modal self-supervised learning

---

## License

This project is intended for academic and research purposes.
