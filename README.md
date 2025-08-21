# surgical-tool-detection-yolov8

Code & scripts for **"Lightweight YOLOv8 Variants for Enhanced Real-Time Surgical Tool Detection"**  
(*PeerJ Computer Science, 2025*)

---

## 1. Repository Structure

<details>
<summary>Click to expand the folder tree</summary>

```text
surgical-tool-detection-yolov8/
├─ README.md
├─ requirements.txt
├─ configs/
│  ├─ data_m2cai.yaml
│  └─ data_surgical_tools.yaml
├─ models/
│  ├─ model1/            # +G + SC3T + C2f-Ghost (example)
│  │  ├─ ultralytics/
│  │  └─ README.md
│  │
│  ├─ model2/            # model1 + CAM + CBAM
│  │  ├─ ultralytics/
│  │  └─ README.md
│  │  
│  └─ model3/            # +G + SC3T + CBAM (best)
│     ├─ ultralytics/
│     └─ README.md
│    
└─ .gitignore
```

</details>

---

## 2. Installation & Setup

### Requirements
Install the required dependencies:

```bash
pip install -r requirements.txt
```

### Dataset Configuration
Configure your dataset paths in the YAML files:
- `configs/data_m2cai.yaml` - for M2CAI dataset
- `configs/data_surgical_tools.yaml` - for surgical tools dataset

---

## 3. Training Guide

For a step-by-step training example, please refer to the Colab notebook:  

👉 [**Open in Google Colab**](https://colab.research.google.com/drive/1W6aJbrVoVKeqEHPcdncOmVnV4aM4Mf7j?usp=sharing)

### Quick Start
```bash
# Example training command
python train.py --config configs/data_surgical_tools.yaml --model model3
```

---

## 4. Citation

If you use this repository, please cite our paper:

```bibtex
@article{nguyen2025surgical,
  title     = {Lightweight YOLOv8 Variants for Enhanced Real-Time Surgical Tool Detection},
  author    = {Tuan Do},
  journal   = {PeerJ Computer Science},
  year      = {2025},
  doi       = {10.5281/zenodo.1234567}
}
```
###Contact: thaikd@vnu.edu.vn (Corresponding Author)

###Funding: Vietnam National University, Hanoi (Project QG.24.63)
