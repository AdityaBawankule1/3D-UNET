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
