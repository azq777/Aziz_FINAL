# 🚗 AI Car Damage Detection with YOLO

This project is a Google Colab / Jupyter Notebook workflow for testing a trained **YOLO** model on multiple vehicle images and detecting visible damage categories.

The notebook provides a simple batch-testing pipeline: upload several images, run object detection, print the predicted damage classes with confidence scores, and display each image with YOLO bounding boxes.

## 🎯 Project Objective

The objective is to demonstrate a practical computer-vision workflow for automated vehicle-damage inspection using a trained YOLO model. The notebook focuses on inference and batch testing rather than model training.

## 🔎 Detected Damage Classes

The notebook is configured for six classes:

```text
1. dent
2. scratch
3. crack
4. glass shatter
5. lamp broken
6. tire flat
```

## 🧠 Workflow

```text
Google Colab
     ↓
Mount Google Drive
     ↓
Load trained YOLO model (best.pt)
     ↓
Upload multiple vehicle images
     ↓
YOLO inference at 640px
     ↓
Confidence filtering
     ↓
Damage labels + confidence scores
     ↓
Bounding-box visualization
```

## 🛠️ Technology Stack

| Component | Technology |
|---|---|
| Notebook | Jupyter Notebook / Google Colab |
| Language | Python |
| Object Detection | Ultralytics YOLO |
| Image Processing | OpenCV |
| Visualization | Matplotlib |
| File Upload | Google Colab `files.upload()` |
| Model Storage | Google Drive in the current notebook workflow |

## 📁 Repository Structure

```text
Aziz_FINAL/
├── Aziz_FINAL.ipynb   # Batch car-damage detection notebook
└── README.md          # Project documentation
```

## ✅ Requirements

The notebook installs the required Python packages with:

```python
pip install ultralytics opencv-python matplotlib
```

A trained YOLO weights file is also required. The current notebook expects a model named `best.pt` at a Google Drive path.

> The trained model file is not included in the current repository. Update `MODEL_PATH` in the notebook to point to your own authorized model weights.

## 🚀 How to Run

1. Open `Aziz_FINAL.ipynb` in Google Colab.
2. Run the dependency-installation cell.
3. Mount Google Drive when prompted.
4. Make sure the trained `best.pt` YOLO weights are available in Drive.
5. Update this line in the notebook if your model is stored elsewhere:

```python
MODEL_PATH = r"/content/drive/MyDrive/.../best.pt"
```

6. Run the notebook.
7. Select multiple vehicle images when the upload dialog appears.
8. Enter a confidence threshold between `0.1` and `0.9`, or press Enter to use the default `0.4`.
9. Review the printed predictions and annotated images.

## ⚙️ Inference Configuration

The notebook runs predictions with settings equivalent to:

```python
results = model.predict(
    source=image_path,
    imgsz=640,
    conf=conf_threshold,
    save=False
)
```

If detections are available, the notebook prints the damage class and confidence percentage. Otherwise, it reports that no damage was detected.

## 📌 Current Scope

This repository contains the **inference/testing notebook** only. It does not currently include:

- the training dataset,
- the YOLO training notebook or pipeline,
- the trained `best.pt` weights,
- model evaluation metrics such as precision, recall, mAP, or confusion matrices.

Those items can be documented or added separately if the project is expanded into a complete training-and-evaluation repository.

## ⚠️ Responsible Use & Limitations

Computer-vision predictions are probabilistic and can be affected by lighting, image quality, camera angle, occlusion, vehicle color, and differences between real-world images and the model's training data.

The output should be treated as an automated screening aid, not as a definitive insurance, repair-cost, safety, or legal assessment.

## 🌿 Version Control Practices

Maintain the notebook with meaningful Git commits that describe real changes. Examples:

```text
feat: add batch image testing
feat: add six vehicle damage classes
fix: validate missing model path
docs: document Colab execution steps
```

Large model weights and private datasets should only be committed when their size, licensing, and privacy conditions allow it. Secrets and personal Drive paths should not be published.

## 🔗 Training Program

This project was completed as part of the **L0-FAE — AI Fundamentals for the Workplace** training program at **SDAIA Academy**, under the supervision of **Abdullah Khalid AlShahrani**.

The portfolio demonstrates the practical application of AI fundamentals in the workplace through prompt engineering, professional writing, information processing, verification and fact-checking, safe and responsible use, and daily task integration.

Official SDAIA Academy GitHub:  
https://github.com/SDAIAAcademy

## 📌 Repository

GitHub: https://github.com/azq777/Aziz_FINAL
