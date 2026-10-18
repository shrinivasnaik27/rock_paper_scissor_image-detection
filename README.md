# Rock Paper Scissors Detection Using YOLOv8

A computer vision project that detects Rock, Paper, and Scissors hand gestures using a custom-trained YOLOv8 object detection model. The project covers dataset acquisition, model training, and image-based prediction.

## Project Overview

This project uses a dataset obtained through Roboflow and the pretrained YOLOv8 Nano model as the starting point for training. The model learns to detect Rock, Paper, and Scissors gestures and can predict these classes in new images.

## Features

- Dataset download using the Roboflow Python package
- Custom object detection model training
- Image-based prediction using a trained checkpoint
- Bounding boxes, class labels, and confidence scores
- Configurable training epochs, image size, and confidence threshold

## Technologies Used

- Python
- Ultralytics YOLOv8
- Roboflow
- PyTorch

## Project Structure

```text
rock-paper-scissors-yolo-detection/
├── train.py
├── predict.py
├── requirements.txt
├── README.md
├── .gitignore
└── images/
    └── stonps.jpg
```

The dataset, model checkpoints, and training results are generated or downloaded locally and are not included by default.

## Requirements

- Python version supported by the installed Ultralytics release
- pip
- A Roboflow account with access to the selected dataset
- A valid Roboflow API key for downloading the dataset
- Sufficient memory and compute resources for model training
- A trained model checkpoint and sample image for prediction

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/rock-paper-scissors-yolo-detection.git
cd rock-paper-scissors-yolo-detection
```

Replace `YOUR-USERNAME` with your GitHub username.

### 2. Create a virtual environment

```bash
python -m venv .venv
```

On Windows:

```bash
.venv\Scripts\activate
```

On macOS or Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

## Dataset Setup and Training

The training script downloads version 1 of the configured Rock, Paper, and Scissors dataset through Roboflow in YOLOv8 format.

Before training, set the `ROBOFLOW_API_KEY` environment variable securely. Never place your real API key in source code or commit it to GitHub.

Run:

```bash
python train.py
```

The training configuration uses:

- Model: YOLOv8 Nano (`yolov8n.pt`)
- Epochs: 25
- Image size: 640
- Batch size: Automatically selected (`-1`)

Training produces model weights and other artifacts in the Ultralytics output directory.

## Image Prediction

Place a sample image at `images/stonps.jpg` and set the model path in `predict.py` to the actual location of the trained `best.pt` checkpoint.

Run:

```bash
python predict.py
```

The prediction result is saved by Ultralytics. The output includes annotated detections when objects are detected.

## Configuration

The confidence threshold is set to `0.5`. It can be adjusted in `predict.py`:

```python
conf=0.5
```

A higher threshold generally filters out more low-confidence predictions, while a lower threshold may retain additional detections.

## Security and Data Handling

- Keep API keys, passwords, tokens, and private configuration files out of GitHub.
- Use environment variables or an approved secret manager for credentials.
- Do not upload datasets, images, or trained weights unless their licenses and sharing permissions allow redistribution.
- The downloaded dataset and trained weights are excluded by default.

## Learning Outcomes

This project demonstrates dataset preparation, transfer learning, custom YOLO model training, object detection inference, and prediction visualization.

## License

Check the dataset terms, pretrained model license, and applicable software licenses before redistributing any associated files. Add a license for your own code if you want to specify reuse permissions.
