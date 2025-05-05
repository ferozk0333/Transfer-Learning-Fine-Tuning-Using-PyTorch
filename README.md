# Transfer Learning on Fashion MNIST using VGG16 (PyTorch)

This project demonstrates **transfer learning** using the pre-trained **VGG16** model on the **Fashion MNIST** dataset using **PyTorch**. I adapted the grayscale images to work with VGG16’s input requirements and fine-tuned the model for improved performance on a smaller, domain-specific dataset.

---

## What is Transfer Learning?

Transfer Learning is a machine learning technique where a model trained on a large dataset (like ImageNet) is adapted to a different but related task (like Fashion MNIST classification), reducing training time and improving performance with limited data.

---

## 🔧 Workflow

1. **Data Preprocessing**
   - Fashion MNIST images (28x28 grayscale) are reshaped and converted to 3-channel (RGB) format
   - Transforms applied: Resize → CenterCrop → ToTensor → Normalize

2. **Custom Dataset Class**
   - Built using PyTorch’s `Dataset` class
   - Applies necessary ETL steps for compatibility with VGG16

3. **Model Setup**
   - Pre-trained VGG16 is loaded from `torchvision.models`
   - Feature extractor layers are **frozen**
   - Classifier head is **replaced** to match 10 Fashion MNIST classes

4. **Training**
   - Model trained using `CrossEntropyLoss` and `Adam` optimizer
   - Fine-tuned only the classification head (fully connected layers)

---

## Requirements

- Python 3.7+
- PyTorch
- torchvision
- numpy
- matplotlib
- PIL

---

Author: Feroz Khan

