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
