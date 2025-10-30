# coarse2fine-height-diffusion
Two-stage conditional diffusion for 10 m height estimation from Sentinel-1/2 with limited LiDAR supervision.

This repository contains the implementation of a two-stage conditional diffusion framework for large-area height estimation at 10 m resolution.

## Method Overview
1. **Stage 1 (Pretraining):** The model is pretrained on low-resolution, open-access surface elevation products (SRTM and COP DEMs, ~30 m). This stage learns large-scale terrain structure and surface height statistics.
2. **Stage 2 (Fine-tuning):** The pretrained model is selectively fine-tuned using a small amount of high-resolution AHN4 LiDAR-derived DSM/DTM data. This enables coarse-to-fine transfer without requiring large-scale LiDAR coverage.

## Inputs
- **Sentinel-1:** dual-polarization InSAR features derived from single-baseline SLC data.
- **Sentinel-2:** multispectral (MS) imagery providing spectral and structural cues.

## Outputs
- DSM (terrain + above-ground objects)
- DTM (bare-earth elevation)
- Object height (DSM − DTM)

## Citation
If you use this code or data pipeline, please cite our work (paper under review).

