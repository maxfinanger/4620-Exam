# Explainable Deep Learning on CIFAR-10: Grad-CAM & LIME

This project implements and compares two state-of-the-art explainable AI (XAI) methods—**Grad-CAM** and **LIME**—on image classification with a fine-tuned ResNet-50 model using the CIFAR-10 dataset. The code and report provide a full pipeline from data preprocessing and model training to XAI visualization and quantitative comparison.

## Project Overview

- **Goal:** Train a robust image classifier on CIFAR-10 and analyze model decisions using Grad-CAM and LIME.
- **Notebook:** All code is in [`xAI_gradcam_lime.ipynb`](xAI_gradcam_lime.ipynb).
- **Report:** See the PDF for detailed analysis and results.

## Model & Dataset

- **Model:** ResNet-50 (ImageNet-pretrained, fine-tuned for CIFAR-10)
  - Final layer replaced with Dropout + Linear for regularization
  - All layers fine-tuned (not just the head)
- **Dataset:** CIFAR-10 (60,000 images, 10 classes)
  - Images resized to 224x224, normalized with ImageNet stats
  - Data augmentation: random crop, horizontal flip, color jitter
  - Train/val/test split: 40k/10k/10k

## Training & Regularization

- **Loss:** CrossEntropyLoss with label smoothing
- **Optimizer:** Adam (weight decay for L2 regularization)
- **Scheduler:** ReduceLROnPlateau (auto LR reduction)
- **Early Stopping:** Based on validation accuracy and per-class accuracy (prevents class collapse)
- **Gradient Clipping:** Prevents exploding gradients

## Explainable AI (XAI) Methods

- **Grad-CAM:** Visualizes class-discriminative regions using gradients from the last convolutional layer
- **LIME:** Generates local explanations by perturbing superpixels and fitting a local surrogate model
- **Comparison:** Side-by-side visualizations and quantitative overlap (IoU) analysis

## Evaluation & Metrics

- **Accuracy:** Overall and per-class accuracy on test set
- **Confusion Matrix:** Visualizes class confusion
- **Sample Predictions:** Shows correct/incorrect predictions with color-coded labels
- **XAI Metrics:**
  - Visual: Grad-CAM and LIME overlays for each class
  - Quantitative: IoU (Intersection over Union) between Grad-CAM and LIME masks, per-class and overall

## Reproducing Results

1. **Install dependencies:**
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   ```
2. **Download CIFAR-10:**
   - The notebook will auto-download if not present in `data/`.
3. **Run the notebook:**
   ```bash
   jupyter lab
   # Open xAI_gradcam_lime.ipynb and run all cells
   ```
4. **Pretrained weights:**
   - Provided: `resnet50_cifar10_anti_overfitting.pth`, `resnet50_cifar10_best.pth`, `resnet50_cifar10_enhanced.pth`
   - To retrain: set `num_epochs` and run training cells

## Dependencies

See [`requirements.txt`](requirements.txt) for all packages, including:

- torch, torchvision, numpy, matplotlib, seaborn, scikit-learn, tqdm, jupyter, ipywidgets
- lime, opencv-python, scikit-image

## Tested Environment

- Python 3.10+
- PyTorch 2.5.1 (CPU or GPU)
- CUDA 11.8+ (optional, for NVIDIA GPUs)
- MPS support (Apple Silicon M1/M2/M3/M4)

---

For details on methodology, results, and interpretation, see the notebook and the report PDF.
