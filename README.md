# surgical-tool-detection-yolov8
Code &amp; scripts for "Lightweight YOLOv8 Variants for Enhanced Real-Time Surgical Tool Detection" (PeerJ Computer Science)

## Repository structure
<details>
<summary>Click to view the folder tree / Bấm để xem cấu trúc thư mục</summary>

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

## Run in Colab
- Model 1: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<your-username>/surgical-tool-detection-yolov8/blob/main/models/model1/train_colab.ipynb)
- Model 2: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<your-username>/surgical-tool-detection-yolov8/blob/main/models/model2/train_colab.ipynb)
- Model 3: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<your-username>/surgical-tool-detection-yolov8/blob/main/models/model3/train_colab.ipynb)
