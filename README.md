# surgical-tool-detection-yolov8
Code &amp; scripts for "Lightweight YOLOv8 Variants for Enhanced Real-Time Surgical Tool Detection" (PeerJ Computer Science)

surgical-tool-detection-yolov8/
├── README.md                 # giới thiệu tổng
├── requirements.txt
├── configs/
│   ├── data_m2cai.yaml
│   └── data_surgical_tools.yaml
├── models/
│   ├── model1/               # +G + SC3T + C2f-Ghost (ví dụ)
│   │   ├── config.yaml
│   │   ├── train_colab.ipynb
│   │   └── README.md
│   ├── model2/               # model1 + CAM + CBAM
│   │   ├── config.yaml
│   │   ├── train_colab.ipynb
│   │   └── README.md
│   └── model3/               # +G + SC3T + CBAM (best)
│       ├── config.yaml
│       ├── train_colab.ipynb
│       └── README.md
└── .gitignore

