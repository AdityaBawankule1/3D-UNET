# 3D U-Net for Volumetric Segmentation

A 3D U-Net implementation for volumetric data segmentation using deep learning, with patch-based training for handling large 3D volumes.

## Overview

This project implements a 3D U-Net architecture for segmentation of volumetric data, particularly useful for:

- Medical image segmentation (CT/MRI scans)

- Geological sample analysis

- Any 3D volumetric data segmentation tasks

The implementation uses a patch-based approach to handle large 3D volumes that exceed GPU memory limits.

## Key Features

1. **3D U-Net Architecture:** Built using segmentation-models-3D library
2. **Patch-based Processing:** Handles large volumes through patchify → train → unpatchify workflow
3. **Memory Efficient:** Processes 64x64x64 patches to fit GPU memory constraints
4. **Comprehensive Training:** 100 epochs with batch size 8
5. **Evaluation Metrics:** IoU (Intersection over Union) for segmentation quality
6. **Visualization Tools:** Training curves and qualitative result displays

## Model Arhitecture

- **Parameters:** ~42 million trainable parameters
- **Backbone:** ResNet-18 (3D version)
- **Input:** 3D patches (64x64x64 voxels)
- **Output:** Segmentation masks with same dimensions

## Dataset Requirement

- 3D volumetric images (medical scans, geological samples, etc.)
- Corresponding segmentation masks/labels
- Supported formats: NIfTI, NumPy arrays, DICOM

## Workflow

**1. Patchify** 
Large 3D volumes are divided into smaller 64x64x64 patches to fit GPU memory:
- Handles volumes of any size
- Overlapping patches for better edge predictions
- Maintains spatial relationships

**2. Training**
- Epochs: 100
- Batch Size: 8
- Loss Function: Segmentation loss (binary crossentropy or dice loss)
- Metrics: IoU (Intersection over Union)
- Optimization: Adam optimizer
  
**3. Unpatchify**
Patch predictions are reconstructed into full-volume segmentations:
- Seamless patch stitching
- Overlap handling for smooth boundaries
- Full volume prediction output
