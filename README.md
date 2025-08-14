# Satellite-Image-Analysis-with-Stable-Diffusion-YOLOv8-
Synthetic satellite imagery generation and YOLOv8 pseudo-labelling pipeline.

# 🌌 Stable Diffusion Satellite Image Generation Pipeline

This repository contains a complete **Stable Diffusion fine-tuning and image generation pipeline** for satellite images, along with **CLIP** and **FID** metric evaluation and automated export of generated outputs.

---

## 📋 Features

- **Fine-tunes Stable Diffusion** on a custom satellite `.tif` dataset.
- **Generates batches** of synthetic satellite images.
- **Converts `.tif` → `.png`** automatically (no `rasterio` required).
- **Evaluates quality** with:
  - **CLIP Score** (image-text similarity)
  - **FID Score** (distribution similarity to real dataset)
- **Visualization outputs** for CLIP/FID metrics.
- **Automatic ZIP exports**:
  - Generated images
  - Metrics folder

---

## 📂 Folder Structure

├── dataset/ # Your input .tif dataset
├── output/
│ ├── batch_50/ # Generated PNG images
│ ├── metrics/ # Metric plots + JSON results
│ │ ├── clip_scores.png
│ │ ├── fid_scores.png
│ │ └── final_metrics.json
│ ├── images_batch_50.zip # Exported generated images
│ └── metrics.zip # Exported metrics folder
├── pipeline.py # Main pipeline script
└── README.md # This file

---

## ⚙️ Requirements

Install dependencies:

```bash
pip install torch torchvision torchaudio
pip install diffusers open-clip-torch
pip install matplotlib pillow numpy
pip install pytorch-fid
```

## 🚀 Usage:

The pipeline will:

Fine-tune Stable Diffusion on your dataset.

Generate synthetic images.

Calculate CLIP & FID metrics.

Save plots and JSON results.

Export two .zip files:

images_batch_X.zip → generated images.

metrics.zip → metric results & plots.

## 📊 Metrics

1. CLIP Score

- Measures semantic alignment between generated images and prompts.
- Output: metrics/clip_scores.png

2. FID Score

- Measures how close generated image distribution is to the real dataset.
- Output: metrics/fid_scores.png

## 📦 Exporting Outputs

The function:

- export_separate_zips(batch_size=50)

Creates:

* images_batch_50.zip → PNGs in batch_50/
* metrics.zip → all files from metrics/

## 🖼 Sample Visualization

Example CLIP score plot:

<img width="1000" height="600" alt="clip_scores" src="https://github.com/user-attachments/assets/53f70687-a194-4bc3-ae07-e5d5461b1063" />

