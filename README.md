# Low-Light Image Enhancement Pipeline

This repository provides a comprehensive approach to **Low-Light Image Enhancement**, exploring both traditional computer vision techniques and deep learning-based solutions. The project aims to improve image quality, reduce noise, and restore detail in underexposed scenarios.

## 🚀 Overview
The project is divided into three distinct phases to evaluate different approaches to image processing:

1.  **Phase 1: Lighting Classification**: Identifying whether an image is low-light or normal using extracted features (mean, std, entropy, skewness) and a Logistic Regression classifier.
2.  **Phase 2: Classical Enhancement**: Applying traditional image processing algorithms (HE, CLAHE, Gamma Correction, and Retinex SSR) and performing visual comparisons.
3.  **Phase 3: Deep Learning Enhancement**: Implementing an `ImprovedAutoencoder` architecture using PyTorch to learn image restoration end-to-end.

## 🛠 Features
- **Data Preprocessing**: Custom `LOLDatasetLoader` for handling the LOL-v2 dataset.
- **Classical Methods**:
  - Histogram Equalization (HE)
  - Contrast Limited Adaptive Histogram Equalization (CLAHE)
  - Gamma Correction
  - Single-Scale Retinex (SSR)
- **Deep Learning Model**: A robust Autoencoder with Skip Connections (U-Net style architecture) for better detail preservation.
- **Quantitative Evaluation**: Performance comparison using **PSNR** (Peak Signal-to-Noise Ratio) and **SSIM** (Structural Similarity Index Measure).

## 📊 Methodology

### The Autoencoder Architecture
The core of the deep learning phase is an `ImprovedAutoencoder` consisting of:
- **Encoder**: 4 blocks of Convolutional layers with LeakyReLU and BatchNorm.
- **Bottleneck**: Deep feature extraction with sequential convolutions.
- **Decoder**: Symmetric upsampling with Skip Connections to combine high-level features with spatial details.

### Metrics
We use two primary metrics to compare classical methods against our deep learning model:
- **PSNR**: Measures the ratio between maximum signal power and noise power.
- **SSIM**: Measures the perceptual similarity between the output and the ground truth.

## 📦 Prerequisites
To run this project, you need the following libraries installed:
```bash
pip install torch torchvision opencv-python scikit-learn matplotlib pandas numpy scikit-image
```

🚀 How to Use

Clone the repository:

 ```bash
git clone https://github.com/yourusername/low-light-enhancement.git
cd low-light-enhancement
```

  Prepare the Dataset: Ensure your LOL-v2 dataset folder structure matches the path definitions in the code (LOL-v2/Real_captured/Train/Low and Normal).
  Run the Notebook: Open the .ipynb file in Jupyter Notebook or VS Code and execute the cells in order.
