# Skin-Lesion-Segmentation-
🩺 Skin Lesion Segmentation using CNN with Attention Mechanism

A deep learning–based approach for automated skin lesion segmentation in dermoscopic images, built with PyTorch.
This model integrates spatial and channel attention mechanisms within a High-Resolution Feature Block (HRFB) to preserve fine edge details and improve lesion boundary detection.

🧠 Overview

Skin lesion segmentation is a crucial step in computer-aided diagnosis for melanoma and other skin cancers.
Conventional CNNs often lose boundary information due to repeated downsampling.
To address this, our architecture combines:

High-Resolution Feature Blocks (HRFBs) for detail preservation

Spatial attention to suppress background noise

Channel-wise attention to emphasize informative features

🏗️ Architecture

The model consists of:

Encoder: Two convolutional layers with batch normalization and ReLU.

HRFB Stack: Three HRFB modules, each containing:

A main 3×3 convolution branch

A spatial attention branch (encoder–decoder with bilinear upsampling)

A channel attention branch (4 convolution layers + squeeze-excitation)

Decoder & Output: 1×1 convolution to generate two-channel score maps (background vs lesion) followed by bilinear upsampling.

⚙️ Features

Implemented using PyTorch

Data augmentation: flips and rotations (8× dataset expansion)

Weighted cross-entropy loss + attention supervision loss (MSE)

Evaluation metrics: Jaccard Index, Dice Coefficient, Accuracy, Sensitivity, Specificity

Visualization of predicted vs ground truth masks
