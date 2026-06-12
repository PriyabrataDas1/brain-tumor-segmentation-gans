# Brain Tumor Segmentation using Deep Learning with GANs

## Overview

Brain tumor segmentation is a critical task in medical image analysis that assists clinicians in diagnosis, treatment planning, and disease monitoring. This project investigates the use of Deep Convolutional Generative Adversarial Networks (DCGANs) for synthetic MRI image generation and data augmentation to improve segmentation performance. A U-Net-based segmentation framework was developed and evaluated on the LGG MRI Segmentation Dataset, and the impact of GAN-generated images on segmentation accuracy was quantitatively assessed.

---

## Objectives

- Develop a U-Net-based brain tumor segmentation framework.
- Generate synthetic MRI images using DCGANs.
- Address limited annotated medical imaging data through augmentation.
- Improve segmentation performance and model generalization.
- Compare baseline and GAN-augmented models using standard evaluation metrics.

---

## Dataset

**LGG MRI Segmentation Dataset**

- Total MRI image-mask pairs: 3,929
- Training samples: 3,339
- Test samples: 590
- Image resolution: 256 × 256 pixels
- MRI images with corresponding tumor masks

### Preprocessing

- Image resizing
- Intensity normalization
- Mask preparation
- Dataset splitting for training and testing

---

## Methodology

The project was conducted in two major stages. First, a baseline U-Net segmentation model was trained using the original MRI dataset. Subsequently, a Deep Convolutional Generative Adversarial Network (DCGAN) was trained on tumor-containing MRI slices to generate synthetic MRI images.

The generated images were incorporated into the training dataset to increase data diversity and reduce overfitting. The U-Net model was then retrained using the augmented dataset, and its performance was compared with the baseline model.

### U-Net Architecture

The segmentation model was based on the U-Net architecture, which is widely used for biomedical image segmentation due to its encoder-decoder structure and skip connections.

Key features include:

- Encoder-decoder architecture
- Skip connections
- Batch normalization
- ReLU activation functions
- Pixel-wise segmentation

### DCGAN Architecture

The augmentation model was implemented using a Deep Convolutional Generative Adversarial Network (DCGAN).

The DCGAN was used to:

- Generate synthetic MRI images
- Increase dataset diversity
- Improve model robustness
- Enhance segmentation accuracy

---

## Experimental Workflow

1. MRI image preprocessing and normalization
2. Baseline U-Net training
3. Baseline performance evaluation
4. DCGAN training on tumor-containing MRI images
5. Synthetic MRI generation
6. Dataset augmentation
7. Retraining of U-Net on augmented data
8. Final evaluation and performance comparison

---

## Results

### Segmentation Performance

| Metric | Baseline U-Net | GAN-Augmented U-Net |
|----------|----------|----------|
| Dice Coefficient | 0.2067 | 0.3037 |
| IoU Score | 0.1243 | 0.1918 |

### Performance Improvement

- Dice Coefficient Improvement: **46.94%**
- IoU Improvement: **54.36%**

The inclusion of GAN-generated MRI images significantly improved segmentation performance, demonstrating the effectiveness of synthetic data augmentation for medical image analysis.

---

## Technologies Used

### Programming

- Python

### Deep Learning

- PyTorch

### Computer Vision

- OpenCV
- NumPy

### Machine Learning

- Scikit-Learn

### Visualization

- Matplotlib

### Development Environment

- Google Colab

---

## Applications

- Brain Tumor Segmentation
- Medical Image Analysis
- Biomedical Image Processing
- AI-Assisted Diagnosis
- Healthcare Imaging
- Clinical Decision Support Systems

---

## Future Work

Potential extensions of this work include:

- Attention U-Net
- U-Net++
- 3D U-Net
- Conditional GANs
- Explainable AI (Grad-CAM)
- Validation on the BraTS Dataset
- Multi-modal MRI Analysis
- Clinical Translation Studies

---

## Repository Structure

```text
brain-tumor-segmentation-gans/

├── README.md
├── Brain_Tumor_Segmentation_using_Deep_Learning_with_GANs.ipynb
├── MINI_PROJECT_REPORT.pdf
└── requirements.txt
```

---

## Conclusion

This study demonstrates that GAN-based data augmentation can substantially improve brain tumor segmentation performance when annotated medical imaging data are limited. By integrating synthetic MRI images into the training process, the model achieved notable improvements in both Dice Coefficient and IoU Score, highlighting the potential of generative AI techniques for biomedical image analysis and healthcare applications.

---

## Author

**Priyabrata Das**  
Biomedical Engineering  
National Institute of Technology Rourkela

---

## Keywords

Brain Tumor Segmentation, U-Net, GAN, DCGAN, Deep Learning, Medical Imaging, MRI Analysis, Biomedical Engineering, Healthcare AI, Computer Vision, PyTorch

---

## Citation

If you use this repository in academic work, research, or educational projects, please cite:

Das, P. *Brain Tumor Segmentation using Deep Learning with GANs*. GitHub Repository, 2026.

Repository:

https://github.com/PriyabrataDas1/brain-tumor-segmentation-gans
