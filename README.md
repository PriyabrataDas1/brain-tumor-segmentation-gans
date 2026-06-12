# Brain Tumor Segmentation using Deep Learning with GANs

## Project Overview

Brain tumor segmentation is a fundamental task in medical image analysis that assists clinicians in diagnosis, treatment planning, and disease monitoring. However, the availability of large annotated medical imaging datasets remains a significant challenge for training robust deep learning models.

This project presents a deep learning framework that combines U-Net-based semantic segmentation with Deep Convolutional Generative Adversarial Networks (DCGANs) for synthetic MRI image generation and dataset augmentation.

The objective was to investigate whether GAN-generated MRI images could improve segmentation performance by increasing training data diversity and reducing overfitting.

---

## Objectives

- Develop an automated brain tumor segmentation framework using U-Net.
- Generate synthetic MRI images using DCGANs.
- Augment the training dataset with GAN-generated images.
- Evaluate the effect of synthetic data on segmentation performance.
- Compare baseline and augmented models using Dice Coefficient and Intersection-over-Union (IoU).

---

## Dataset

### LGG MRI Segmentation Dataset

The project utilizes the publicly available LGG-MRI dataset containing MRI images and corresponding tumor masks.

Dataset Statistics:

- Total MRI image-mask pairs: 3,929
- Patient directories: 112
- Training samples: 3,339
- Test samples: 590
- Image resolution: 256 × 256 pixels

### Preprocessing

- Grayscale conversion
- Image resizing to 256 × 256
- Intensity normalization
- Binary mask generation
- Train-test split (85:15)

---

## Methodology

### Phase 1: Baseline Brain Tumor Segmentation

A custom U-Net architecture was implemented for pixel-wise brain tumor segmentation.

#### U-Net Features

- Encoder-decoder architecture
- Skip connections
- Batch normalization
- ReLU activations
- Binary segmentation output

#### Model Statistics

- Total parameters: 31,042,369
- Optimizer: Adam
- Learning Rate: 0.001
- Loss Function: Binary Cross Entropy (BCE)
- Training Epochs: 15

---

### Phase 2: GAN-Based Data Augmentation

A Deep Convolutional Generative Adversarial Network (DCGAN) was trained to generate synthetic MRI images containing tumor structures.

#### Generator

- Fully connected latent projection
- Progressive transpose convolutions
- Batch normalization
- ReLU activations
- Tanh output layer

#### Discriminator

- Convolutional feature extraction
- LeakyReLU activations
- Batch normalization
- Sigmoid classification output

#### GAN Statistics

- Generator Parameters: 7,308,449
- Discriminator Parameters: 694,113
- GAN Training Epochs: 20

---

### Phase 3: Synthetic Data Generation

The GAN was trained exclusively on tumor-containing MRI slices.

Dataset Used for GAN Training:

- Tumor-containing MRI images: 1,141

Synthetic Dataset Generated:

- Synthetic MRI images: 3,339
- Synthetic masks: 3,339

Training Dataset Expansion:

- Original dataset: 3,339 samples
- Augmented dataset: 6,678 samples

---

### Phase 4: Augmented Model Training

A second U-Net model was trained using the combined real and synthetic dataset.

Training configuration remained identical to the baseline model to ensure a fair comparison.

---

## Experimental Workflow

1. Download and preprocess MRI images.
2. Train baseline U-Net model.
3. Evaluate baseline segmentation performance.
4. Train DCGAN on tumor-containing MRI slices.
5. Generate synthetic MRI images.
6. Create pseudo-segmentation masks.
7. Augment training dataset.
8. Retrain U-Net using augmented data.
9. Evaluate segmentation performance.
10. Compare baseline and augmented models.

---

## Results

### Baseline U-Net

Dice Coefficient:

0.2067

IoU Score:

0.1243

---

### GAN-Augmented U-Net

Dice Coefficient:

0.3037

IoU Score:

0.1918

---

### Performance Improvement

Dice Coefficient Improvement:

46.94%

IoU Improvement:

54.36%

---

## Key Findings

### Improved Generalization

GAN-generated MRI images increased dataset diversity and enabled the model to generalize better to unseen test data.

### Reduced Data Scarcity

The augmentation pipeline effectively doubled the training dataset size without requiring additional manual annotations.

### Enhanced Segmentation Accuracy

Both Dice and IoU metrics improved substantially after GAN augmentation.

### Better Model Robustness

The augmented model exhibited lower validation loss and improved consistency during testing.

---

## Technologies Used

Programming & Development

- Python
- Google Colab

Deep Learning

- PyTorch
- TorchMetrics

Computer Vision

- OpenCV
- NumPy

Machine Learning

- Scikit-Learn

Visualization

- Matplotlib

---

## Applications

- Brain Tumor Segmentation
- Medical Image Analysis
- Biomedical Image Processing
- AI-Assisted Diagnosis
- Clinical Decision Support
- Healthcare Imaging
- Deep Learning for Radiology

---

## Future Work

Potential improvements include:

- Attention U-Net
- U-Net++
- 3D U-Net
- Conditional GANs
- Diffusion Models
- Explainable AI (Grad-CAM)
- Multi-modal MRI Analysis
- Validation on BraTS Dataset
- Clinical Translation Studies

---

## Repository Structure

brain-tumor-segmentation-gans/

├── README.md

├── Brain_Tumor_Segmentation_using_Deep_Learning_with_GANs.ipynb

├── Brain_Tumor_Segmentation_Report.pdf

├── results/

│   ├── baseline_predictions.png

│   ├── gan_generated_images.png

│   ├── performance_comparison.png

│   └── project_summary.png

└── requirements.txt

---

## Conclusion

This study demonstrates that GAN-based data augmentation can significantly improve brain tumor segmentation performance when annotated medical imaging data is limited.

By generating 3,339 synthetic MRI images and incorporating them into the training process, the segmentation framework achieved:

- 46.94% improvement in Dice Coefficient
- 54.36% improvement in IoU Score

The results highlight the potential of generative AI techniques for addressing data scarcity challenges in medical image analysis and improving the reliability of deep learning-based diagnostic systems.

---

## Author

**Priyabrata Das**

Biomedical Engineering

National Institute of Technology Rourkela

---

## Keywords

Brain Tumor Segmentation, U-Net, GAN, DCGAN, Deep Learning, Medical Imaging, MRI Analysis, Computer Vision, Healthcare AI, Biomedical Engineering, PyTorch

---

## Citation

If you use this repository in academic work, research, or educational projects, please cite:

Das, P. *Brain Tumor Segmentation using Deep Learning with GANs*. GitHub Repository, 2026.

Repository:

https://github.com/PriyabrataDas1/brain-tumor-segmentation-gans
