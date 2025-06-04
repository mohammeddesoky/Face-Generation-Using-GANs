# 🧠 Face Generation with GANs

## 📌 Overview
This project implements a **Generative Adversarial Network (GAN)** to generate synthetic but realistic human faces. The model is trained on a Kaggle facial dataset and learns to create new faces from noise vectors. The generator improves through adversarial training against a discriminator that learns to distinguish real faces from fake ones.

## 🧪 Dataset

- **Source:** [Kaggle Facial Dataset (e.g., CelebA or UTKFace)](https://www.kaggle.com/datasets/jessicali9530/celeba-dataset)
- **Content:** Thousands of human face images in various angles, genders, and ethnicities
- **Preprocessing:**
  - Resized to 64x64
  - Normalized pixel values [-1, 1]
  - Augmented with flipping and cropping

## 🧠 Model Architecture

### Generator
- Input: 100-dimensional noise vector
- Layers: Fully Connected → BatchNorm → LeakyReLU → Transposed Conv

### Discriminator
- Input: 3x64x64 image
- Layers: Convolution → LeakyReLU → Dropout
- Output: Single sigmoid value (real or fake)

## 🔁 Training Strategy

- Optimizer: Adam (lr=0.0002, beta1=0.5)
- Loss: Binary Cross-Entropy
- Epochs: 800
- Batch Size: 128
- GAN Training Loop: 
  - Train discriminator on real + generated images
  - Train generator to fool the discriminator

## 🛠️ Technologies

- Python  
- TensorFlow
- NumPy  
- Matplotlib
- Kaggle Datasets  
