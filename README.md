# Fish Classification with Segmentation and Data Augmentation

## Overview

This project develops a deep learning pipeline capable of identifying fish species from real-world images affected by varying lighting conditions, image quality, orientations, and background clutter. The system combines image segmentation, data augmentation, and transfer learning to improve classification performance and robustness.

The final model achieved:

* **95.08% Test Accuracy**
* **91.23% Validation Accuracy**
* Classification across **12 fish species**
* Dataset of approximately **3,000 images**

---

## Motivation

Accurate fish species identification is important for sustainable fishing practices, ecological monitoring, fisheries management, and conservation efforts. Traditional identification methods often require expertise and can be prone to human error.

This project explores how deep learning can automate fish identification while remaining robust to challenging real-world image conditions such as poor lighting, motion blur, background clutter, and image distortions.

---

## Methodology

### Fish Segmentation

A pretrained segmentation model (SAM3 via Roboflow) was used to detect and isolate fish within each image. Images were cropped around detected fish before classification to reduce background noise and improve feature extraction.

### Data Augmentation

To improve model generalization, randomized augmentations were applied during training:

* Gaussian Blur
* Horizontal Flips
* Rotation
* Brightness Adjustments

### Transfer Learning

A pretrained ResNet18 model was fine-tuned for fish classification. Transfer learning allowed the model to leverage previously learned visual features while requiring significantly less training data.

### Model Optimization

Several techniques were implemented to reduce overfitting and improve performance:

* Dropout (0.4)
* L2 Weight Decay
* Dataset Refinement
* Class Balancing
* Confusion Matrix Analysis

---

## Results

| Metric              | Performance   |
| ------------------- | ------------- |
| Test Accuracy       | 95.08%        |
| Validation Accuracy | 91.23%        |
| Number of Classes   | 12            |
| Dataset Size        | ~3,000 Images |

The segmentation-based pipeline consistently outperformed the non-segmented baseline and improved classification performance across nearly all fish species.

---

## Technologies Used

* Python
* PyTorch
* ResNet18
* Roboflow
* SAM3 Segmentation
* NumPy
* Scikit-Learn
* Matplotlib
* PIL

---

## Project Workflow

1. Collect fish images from public datasets.
2. Detect and crop fish using a segmentation model.
3. Apply data augmentation during training.
4. Train a ResNet18 classifier using transfer learning.
5. Evaluate performance using accuracy, recall, and confusion matrices.
6. Predict fish species from new input images.

---

## Future Improvements

* Expand dataset size and diversity
* Implement advanced segmentation models such as Mask R-CNN or U-Net
* Experiment with larger architectures such as ResNet50 and EfficientNet
* Explore synthetic data generation using GANs
* Improve classification of visually similar species

---

## Authors

* Sebastian Bessoudo
* Aaron Francis Lerma
* Shanwen Lo
