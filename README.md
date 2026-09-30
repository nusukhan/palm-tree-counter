# 🌴 Palm Tree Counter — AI Object Detection

An AI system that automatically detects and counts palm trees in
aerial / drone imagery using deep learning (YOLO object detection).

---

## 📌 Overview

This project trains an object-detection model to locate every palm tree
in an aerial image with a bounding box, then counts them. It works on
both **images** and **videos**, drawing boxes and a live tree count on
each frame.

Useful for: agriculture, plantation management, and land surveying.

---

## 🛠️ Tech Stack

- **YOLO26n (Ultralytics)** — object detection model
- **OpenCV** — frame-by-frame video processing
- **Roboflow** — labeled palm-tree dataset
- **Google Colab (GPU)** — model training
- **Python**

---

## 📊 Results

| Metric | Score |
|--------|-------|
| mAP50 (test images) | **0.994** |
| mAP50-95 (test images) | **0.918** |
| Trees detected in one image | **94** |
| Video processed | 817 frames, ~22–38 trees per frame |

---

## 🚀 How It Works

1. **Dataset** — labeled palm-tree images downloaded from Roboflow (YOLO format)
2. **Training** — YOLO26n fine-tuned on the dataset using transfer learning
3. **Image detection** — the model predicts boxes and counts trees in a single image
4. **Video detection** — OpenCV reads the video frame by frame; the model
   detects trees in each frame, draws boxes, writes a "Trees: N" count,
   and saves an annotated output video

---

## ⚠️ Limitations

The model performs excellently on **top-down aerial views** but shows
reduced accuracy on **dense / ground-level footage** (out-of-distribution),
where trees overlap and are seen from an angle not present in the training
data.

**Future work:** add labeled data of dense/overlapping views and fine-tune
to improve performance on those cases.

---

## 📁 Files

- `palmtreecounter.ipynb` — full Colab notebook (training + detection)
- `best.pt` — trained model weights
- `output_tree_detection.mp4` — sample annotated video

---

## 👤 Author

**Nusrat** — AI Engineering student
