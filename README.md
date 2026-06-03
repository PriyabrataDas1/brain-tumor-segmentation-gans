# Brain Tumor Segmentation using Deep Learning with GANs

## Overview

This project investigates brain tumor segmentation from MRI images using a U-Net architecture enhanced through GAN-based synthetic data augmentation.

A Deep Convolutional Generative Adversarial Network (DCGAN) was trained to generate synthetic MRI images, helping address the challenge of limited annotated medical imaging datasets.

The generated images were combined with real MRI scans to improve segmentation performance.

---

## Dataset

### LGG MRI Segmentation Dataset

* MRI Images and Corresponding Masks
* Total Dataset Size: 3929 image-mask pairs
* Training Samples: 3339
* Test Samples: 590
* Images resized to 256 × 256 pixels
* Normalized for deep learning training

---

## Models Used

### U-Net

U-Net is a convolutional neural network architecture designed specifically for biomedical image segmentation.

**Features:**

* Encoder-Decoder Architecture
* Skip Connections
* Batch Normalization
* ReLU Activations
* Pixel-wise Segmentation

### DCGAN

Deep Convolutional Generative Adversarial Network (DCGAN)

**Purpose:**

* Generate synthetic MRI images
* Improve dataset diversity
* Reduce overfitting
* Enhance segmentation performance

---

## Workflow

1. Download and preprocess MRI images.
2. Train DCGAN to generate synthetic MRI samples.
3. Combine synthetic and real images.
4. Train U-Net segmentation model.
5. Evaluate using Dice Coefficient and IoU Score.
6. Compare baseline and GAN-augmented performance.

---

## Results

| Metric           | Baseline U-Net | GAN-Augmented U-Net |
| ---------------- | -------------- | ------------------- |
| Dice Coefficient | 0.2067         | 0.3037              |
| IoU Score        | 0.1243         | 0.1918              |

### Performance Improvement

* Dice Score Improvement: **46.94%**
* IoU Improvement: **54.36%**

The inclusion of GAN-generated MRI images significantly improved segmentation performance.

---

## Technologies Used

* Python
* PyTorch
* NumPy
* OpenCV
* Matplotlib
* Scikit-Learn
* Google Colab

---

## Applications

* Brain Tumor Detection
* Medical Image Analysis
* MRI Segmentation
* Biomedical Engineering
* AI-assisted Diagnosis
* Healthcare Imaging

---

## Future Work

* Attention U-Net
* U-Net++
* 3D U-Net
* Conditional GANs
* Explainable AI (Grad-CAM)
* Validation on BraTS Dataset
* Clinical Translation Studies

---

## Repository Structure

```text
brain-tumor-segmentation-gans/
│
├── README.md
├── Brain_Tumor_Segmentation_using_Deep_Learning_with_GANs.ipynb

```

---

## Author

**Priyabrata Das**
Biomedical Engineering
National Institute of Technology Rourkela

---

## Keywords

Brain Tumor Segmentation, U-Net, GAN, DCGAN, Deep Learning, MRI, Medical Imaging, PyTorch, Biomedical Engineering, Computer Vision

## Citation

If you use this repository in your research or academic work, please cite:

**Priyabrata Das.** *Brain Tumor Segmentation using Deep Learning with GANs.* GitHub Repository, 2026.

Available at: https://github.com/PriyabrataDas1/brain-tumor-segmentation-gans
