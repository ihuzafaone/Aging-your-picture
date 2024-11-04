# Face Aging with GANs

A deep learning model that uses CycleGAN to perform face aging transformations, allowing for realistic and high-speed aging effects on facial images. This model can age or rejuvenate facial images without requiring a face detection pipeline, making it ideal for real-time applications.

## Table of Contents

- [Overview](#overview)
- [Examples](#examples)
- [Performance](#performance)
- [Quick Start](#quick-start)
- [Running Inference](#running-inference)
- [Training Your Own Model](#training-your-own-model)
  - [Data Preparation](#data-preparation)
  - [Configuring and Training](#configuring-and-training)
- [Monitoring with TensorBoard](#monitoring-with-tensorboard)
- [Acknowledgments](#acknowledgments)

## Overview

This model, built on CycleGAN, transforms young faces into aged versions and vice versa. It is optimized for processing 512x512 images with a 256x256 central face region, allowing high frame rates and eliminating the need for separate face detection.

## Examples

The examples below show the aging transformation:

| Input (Young Face)       | Output (Aged Face)       |
|--------------------------|--------------------------|
| ![young_face_example]()  | ![aged_face_example]()   |

## Performance

- **Speed:** Achieves 66 FPS on NVIDIA GTX1080 for 512x512 images.
- **Detection-Free:** No need for a face detection pipeline; it works on any 512x512 image containing a 256x256 or larger face region.

## Quick Start

### Running Inference

To apply the pre-trained model to your images, run:

```bash
python infer.py --image_dir 'path/to/your/image/directory'
