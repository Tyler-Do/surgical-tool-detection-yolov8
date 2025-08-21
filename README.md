# surgical-tool-detection-yolov8
Code &amp; scripts for "Lightweight YOLOv8 Variants for Enhanced Real-Time Surgical Tool Detection" (PeerJ Computer Science)

## Repository structure
<details>
<summary>Click to view the folder tree </summary>

```text
surgical-tool-detection-yolov8/
├─ README.md
├─ requirements.txt
├─ configs/
│  ├─ data_m2cai.yaml
│  └─ data_surgical_tools.yaml
├─ models/
│  ├─ model1/            # +G + SC3T + C2f-Ghost (ví dụ)
│  │  ├─ ultralytics
│  │  ├─ README.md
│  │
│  ├─ model2/            # model1 + CAM + CBAM
│  │  ├─ ultralytics
│  │  ├─ README.md
│  │  
│  └─ model3/            # +G + SC3T + CBAM (best)
│     ├─ ultralytics
│     ├─ README.md
│    
└─ .gitignore

## Guidance for Training Yolov8_Transformer.ipynb
--https://colab.research.google.com/drive/1W6aJbrVoVKeqEHPcdncOmVnV4aM4Mf7j?usp=sharing
<!-- HERO -->
<p align="center">
  <img src="assets/hero.png" alt="Surgical Tool Detection YOLOv8" width="75%">
</p>

<h1 align="center">Lightweight YOLOv8 for Real-Time Surgical Tool Detection</h1>
<p align="center">
  <i>PeerJ Computer Science — Code & Reproducibility Pack</i>
</p>

<p align="center">
  <a href="https://github.com/<USER>/<REPO>/actions"><img alt="CI" src="https://img.shields.io/github/actions/workflow/status/<USER>/<REPO>/ci.yml?label=CI&logo=githubactions"></a>
  <a href="https://github.com/<USER>/<REPO>/releases"><img alt="Release" src="https://img.shields.io/github/v/release/<USER>/<REPO>?color=blueviolet&label=release"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/License-MIT-brightgreen.svg"></a>
  <img alt="Python" src="https://img.shields.io/badge/Python-3.11-3776AB?logo=python&logoColor=white">
  <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-2.x-EE4C2C?logo=pytorch&logoColor=white">
  <img alt="Ultralytics" src="https://img.shields.io/badge/Ultralytics-8.x-4A90E2?logo=ultralytics&logoColor=white">
  <a href="https://doi.org/<CODE_DOI>"><img alt="DOI" src="https://img.shields.io/badge/Code%20DOI-<CODE_DOI>-blue"></a>
  <a href="#data--code-availability"><img alt="Data" src="https://img.shields.io/badge/Data-DOI%20inside-FFB000"></a>
  <a href="https://github.com/<USER>/<REPO>/stargazers"><img alt="Stars" src="https://img.shields.io/github/stars/<USER>/<REPO>?style=social"></a>
</p>

<p align="center">
  <a href="https://colab.research.google.com/github/<USER>/<REPO>/blob/main/models/model1/train_colab.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Run Model 1 in Colab">
  </a>
  <a href="https://colab.research.google.com/github/<USER>/<REPO>/blob/main/models/model2/train_colab.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Run Model 2 in Colab">
  </a>
  <a href="https://colab.research.google.com/github/<USER>/<REPO>/blob/main/models/model3/train_colab.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Run Model 3 in Colab">
  </a>
</p>

---

## 🔎 Highlights
- ⚡ **Real-time** inference with lightweight YOLOv8 variants (GhostConv, SC3T, CBAM/CAM).
- 🧪 **Reproducible**: scripts + Colab + versioned configs; Code/Data archived with **DOI**.
- 🛠️ **Three models** (Model1/2/3) — trade-off between accuracy, params and FLOPs.

---

## 📸 Results preview
<p align="center">
  <img src="assets/preds_grid.jpg" alt="Predictions gallery" width="85%">
</p>

---

## 📦 Model Zoo (m2cai16-tool-locations)
| Model | Modules | Loss | mAP@0.5 | Params (M) | GFLOPs | Colab |
|---|---|---|---:|---:|---:|---|
| Baseline | – | CIoU | 94.50 | 11.10 | 28.50 | – |
| **Model 1** | +Ghost + SC3T + C2f-Ghost | CIoU | 94.50 (pretrain) | 2.48 | 9.30 | [Open](models/model1/train_colab.ipynb) |
| **Model 2** | Model1 + CAM + CBAM | CIoU | 95.20 (pretrain) | 4.56 | 14.80 | [Open](models/model2/train_colab.ipynb) |
| **Model 3 (best)** | +Ghost + SC3T + **CBAM** | **SIoU** | **95.70 (pretrain)** | 3.48 | 15.50 | [Open](models/model3/train_colab.ipynb) |

*Numbers from the paper; see tables in the manuscript.*

---

## 🚀 Quick start

<details>
<summary><b>▶ Local (venv)</b></summary>

```bash
git clone https://github.com/<USER>/<REPO>.git && cd <REPO>
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
bash scripts/download_data.sh   # uses Zenodo DOIs
DATA=configs/data_m2cai.yaml
bash scripts/train.sh models/model3/config.yaml $DATA 100 16 640
bash scripts/eval.sh runs/detect/model3/weights/best.pt $DATA 640
