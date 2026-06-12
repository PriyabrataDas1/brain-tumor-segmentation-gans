# Brain Tumor Segmentation using Deep Learning with GANs

Brain tumor MRI segmentation using a U-Net architecture enhanced through GAN-based synthetic data augmentation. Developed using PyTorch and evaluated on the LGG MRI Segmentation Dataset containing 3,929 image-mask pairs.

---

## Overview

Brain tumor segmentation is a critical task in medical image analysis that supports diagnosis, treatment planning, and disease monitoring. While deep learning architectures such as U-Net have demonstrated strong segmentation performance, their effectiveness is often constrained by the limited availability of annotated medical imaging datasets.

This project investigates the use of Deep Convolutional Generative Adversarial Networks (DCGANs) for synthetic MRI image generation and dataset augmentation. A custom U-Net segmentation framework was trained on the LGG MRI Segmentation Dataset and subsequently retrained using GAN-generated synthetic images to evaluate the impact of data augmentation on segmentation performance.

The study demonstrates that synthetic MRI generation can substantially improve segmentation accuracy and model generalization while reducing the effects of data scarcity.

---

## Objectives

* Develop a U-Net-based framework for brain tumor segmentation.
* Generate synthetic MRI images using a DCGAN architecture.
* Address limited training data through GAN-based augmentation.
* Improve segmentation accuracy and model robustness.
* Quantitatively evaluate performance using Dice Coefficient and IoU metrics.

---

## Dataset

### LGG MRI Segmentation Dataset

The project utilizes the TCGA Lower Grade Glioma (LGG-MRI) dataset consisting of MRI scans and corresponding tumor masks.

Dataset statistics:

* Total image-mask pairs: 3,929
* Training samples: 3,339
* Testing samples: 590
* Image resolution: 256 × 256 pixels

### Preprocessing

Prior to training, all images underwent preprocessing to ensure consistency and improve model convergence.

* Image resizing to 256 × 256 pixels
* Intensity normalization
* Binary mask preparation
* Dataset partitioning using an 85:15 train-test split

---

## Methodology

The proposed framework consists of two independent segmentation pipelines. The baseline pipeline employs a custom U-Net architecture trained solely on real MRI images. The second pipeline incorporates synthetic MRI samples generated using a Deep Convolutional Generative Adversarial Network (DCGAN).

Following GAN training, synthetic MRI images were generated and combined with the original training dataset, effectively doubling the number of training samples. A second U-Net model with identical architecture and training parameters was then trained on the augmented dataset to provide a fair comparison between baseline and augmented approaches.

### U-Net Architecture

The segmentation model is based on a custom U-Net implementation containing four encoder blocks, four decoder blocks, and a bottleneck layer. Skip connections are utilized to preserve spatial information and improve reconstruction accuracy.

Key architectural features:

* Encoder-decoder architecture
* Skip connections
* Batch normalization
* ReLU activation functions
* Pixel-wise binary segmentation

Model statistics:

* Total trainable parameters: 31,042,369
* Optimizer: Adam
* Loss function: Binary Cross Entropy (BCE)
* Training epochs: 15

### DCGAN Architecture

A Deep Convolutional Generative Adversarial Network (DCGAN) was implemented to learn the distribution of tumor-containing MRI slices.

The GAN framework consists of:

* Generator network for synthetic MRI creation
* Discriminator network for real/fake classification
* Adversarial optimization strategy
* 20 training epochs

The trained generator was used to create realistic synthetic MRI images for dataset augmentation.

### Synthetic Data Augmentation

To address training data scarcity, the GAN-generated images were incorporated into the original training dataset.

Augmentation statistics:

* Tumor-containing MRI images used for GAN training: 1,141
* Synthetic MRI images generated: 3,339
* Original training samples: 3,339
* Augmented training samples: 6,678

---

## Experimental Workflow

1. MRI image preprocessing and normalization.
2. Baseline U-Net training on original data.
3. Baseline segmentation evaluation.
4. DCGAN training using tumor-containing MRI slices.
5. Generation of synthetic MRI images.
6. Dataset augmentation with synthetic samples.
7. Retraining of U-Net on augmented data.
8. Final evaluation and performance comparison.

---

## Key Results

* Generated 3,339 synthetic MRI images using DCGAN.
* Expanded the training dataset from 3,339 to 6,678 samples.
* Improved Dice Coefficient by 46.94%.
* Improved IoU Score by 54.36%.
* Reduced validation loss and improved model generalization.

---

## Results

The inclusion of GAN-generated MRI images resulted in a substantial improvement in segmentation performance. The augmented model demonstrated superior tumor boundary delineation, improved region localization, and enhanced generalization compared to the baseline model.

| Metric           | Baseline U-Net | GAN-Augmented U-Net |
| ---------------- | -------------- | ------------------- |
| Dice Coefficient | 0.2067         | 0.3037              |
| IoU Score        | 0.1243         | 0.1918              |

### Performance Improvement

* Dice Coefficient Improvement: **46.94%**
* IoU Improvement: **54.36%**

The augmented model also achieved a lower and more stable validation loss, indicating reduced overfitting and improved robustness on unseen MRI data.

---

## Technologies Used

### Programming

* Python

### Deep Learning

* PyTorch

### Computer Vision

* OpenCV
* NumPy

### Machine Learning

* Scikit-Learn

### Visualization

* Matplotlib

### Development Environment

* Google Colab

---

## Applications

* Brain Tumor Segmentation
* Medical Image Analysis
* Biomedical Image Processing
* Computer-Aided Diagnosis
* AI-Assisted Healthcare
* Clinical Decision Support Systems

---

## Future Work

Potential future improvements include:

* Attention U-Net
* U-Net++
* 3D U-Net
* Conditional GANs
* Explainable AI (Grad-CAM)
* BraTS Dataset Validation
* Multi-modal MRI Analysis
* Clinical Translation Studies

---

## Repository Structure

```text
brain-tumor-segmentation-gans/

├── README.md
├── Brain_Tumor_Segmentation_using_Deep_Learning_with_GANs.ipynb
├── Brain_Tumor_Segmentation_GANs_Report.pdf
├── requirements.txt
└── LICENSE
```

---

## Conclusion

This project demonstrates that GAN-based synthetic data augmentation can effectively address data scarcity in medical image segmentation tasks. By incorporating realistic synthetic MRI images into the training process, the segmentation framework achieved significant improvements in both Dice Coefficient and IoU metrics while exhibiting improved generalization and reduced overfitting.

The results highlight the potential of generative deep learning techniques for developing more reliable and clinically relevant AI-assisted medical imaging systems.

---

## Author

**Priyabrata Das**
Biomedical Engineering
National Institute of Technology Rourkela

GitHub: https://github.com/PriyabrataDas1

LinkedIn: https://www.linkedin.com/in/priyabrata-das-74244033b/

---

## Keywords

Brain Tumor Segmentation, U-Net, GAN, DCGAN, Deep Learning, Medical Imaging, MRI Analysis, Biomedical Engineering, Healthcare AI, Computer Vision, PyTorch

---

## Citation

If you use this repository in academic work, research, or educational projects, please cite:

Das, P. *Brain Tumor Segmentation using Deep Learning with GANs*. GitHub Repository, 2026.

Repository:

https://github.com/PriyabrataDas1/brain-tumor-segmentation-gans

