# IlluC-Net: An Attention-Guided U-Net for Illumination Correction in Dermatological Macro-Photographs

## Overview

Uneven illumination in dermatological macro-photographs can significantly degrade the performance of automated diagnostic systems, including lesion segmentation, classification, and texture analysis. Traditional enhancement methods struggle to handle challenging lighting artifacts like shadows, hotspots, and local under-exposure, often over-correcting images or destroying clinically meaningful information.

**IlluC-Net** is a novel **attention-guided U-Net architecture** designed specifically for illumination correction in dermatological macro-images. By integrating spatial attention into an enhanced U-Net backbone, IlluC-Net effectively normalizes illumination while preserving fine-grained skin structures essential for clinical interpretation.

---

## Key Features

- **Attention-Enhanced U-Net Architecture**  
  Integrates spatial attention modules into skip connections for improved focus on under- or over-illuminated regions.

- **End-to-End Illumination Correction**  
  Produces uniformly illuminated images without sacrificing dermatological texture details.

- **Robust Against Illumination Artifacts**  
  Handles shadows, glare, brightness inconsistencies, lens reflections, and micro-illumination variations.

- **Pretrained Model Included**  
  Allows immediate testing and fine-tuning for custom datasets.

- **Modular & Clean Codebase**  
  Designed for research use, extension, and integration into medical imaging pipelines.

---

## Model Architecture

IlluC-Net combines:

- A **U-Net encoder-decoder backbone** for dense image-to-image correction.
- **Spatial Attention Modules** to emphasize illumination-affected areas.
- Optional **residual refinement blocks** for deeper feature propagation.

This hybrid design ensures a balance between local detail preservation and global illumination normalization.

---

# Performance Evaluation

IlluC-Net was evaluated on 100 curated dermatological test images with diverse illumination artifacts. It outperformed several state-of-the-art models in both pixel-level and perceptual metrics.

---

## Table 1 — Quantitative Comparison on 100-Test Images  
*(mean ± standard deviation; best results in bold)*

| Method | PSNR ↑ | SSIM ↑ | MSE ↓ | Entropy ↑ | BRISQUE ↓ | PIQE ↓ | NIQE ↓ |
|--------|--------|--------|--------|------------|-----------|-----------|-----------|
| U-Net [25] (2020) | 31.55 ± 4.95 | 0.96 ± 0.01 | 0.027 ± 0.001 | 6.85 ± 0.14 | 35.48 ± 2.46 | 49.06 ± 7.84 | 0.31 ± 0.03 |
| StillGAN [26] (2021) | 28.92 ± 6.42 | 0.79 ± 0.12 | 0.028 ± 0.002 | 6.57 ± 0.30 | 29.96 ± 5.58 | 49.04 ± 3.19 | 0.31 ± 0.04 |
| EnlightenGAN [27] (2021) | 30.22 ± 2.02 | 0.82 ± 0.06 | 0.033 ± 0.005 | 6.78 ± 0.23 | 47.28 ± 0.88 | 48.07 ± 0.53 | 0.32 ± 0.02 |
| TransUNet [29] (2022) | 33.23 ± 1.01 | 0.88 ± 0.04 | 0.031 ± 0.001 | 6.76 ± 0.25 | 48.32 ± 6.95 | 46.91 ± 6.25 | 0.30 ± 0.02 |
| CSwin-P [31] (2023) | 32.83 ± 0.41 | 0.82 ± 0.03 | 0.029 ± 0.001 | 6.47 ± 0.23 | 61.94 ± 1.09 | 54.59 ± 3.27 | 0.25 ± 0.02 |
| IECET [21] (2024) | 26.22 ± 3.31 | 0.77 ± 0.02 | 0.041 ± 0.002 | 6.45 ± 0.08 | 35.25 ± 6.76 | 62.53 ± 6.34 | 0.52 ± 0.05 |
| Suchitra et al. [34] (2025) | 23.63 ± 0.39 | 0.76 ± 0.01 | 0.044 ± 0.004 | 6.75 ± 0.07 | 40.17 ± 8.49 | 65.78 ± 4.17 | 0.51 ± 0.03 |
| **IlluC-Net (Proposed)** | **35.99 ± 3.15** | **0.98 ± 0.01** | **0.026 ± 0.002** | 6.70 ± 0.25 | **27.09 ± 10.43** | **44.39 ± 9.77** | **0.27 ± 0.02** |

---

## Table 2 — Model Complexity & Inference Time

| Method | Parameters (M) | Inference Time per Image (ms) |
|--------|----------------|-------------------------------|
| U-Net [25] (2020) | 30.8 | 90 |
| StillGAN [26] (2021) | 42.4 | 150 |
| EnlightenGAN [27] (2021) | 36.2 | 110 |
| TransUNet [29] (2022) | 41.4 | 100 |
| CSwin-P [31] (2023) | 72.8 | 92 |
| IECET [21] (2024) | 10.5 | 170 |
| Suchitra et al. [34] (2025) | – | 110 |
| **IlluC-Net (Proposed)** | **31.3** | **90** |

---

## Installation

```bash
git clone https://github.com/your-username/IlluC-Net.git
cd IlluC-Net
pip install -r requirements.txt
```


## Citation

If you use this work, please cite:

```bibtex

```
