# 👁️ MyRealtimeFaceApp: Real-time Face Analysis and Recognition

This project leverages computer vision and deep learning to perform **real-time (or static image) face detection**, analyze attributes like **age, gender, race, and emotion** using **DeepFace**, and identify known individuals using the **face_recognition** library.

It is designed to:
- Process **live webcam streams**, or
- Analyze **individual image files**, while saving both **visual** and **textual** analysis outputs.

---

## 🚀 Features

✅ OpenCV for robust image and video stream processing  
✅ DeepFace integration for highly accurate age, gender, race, and emotion analysis  
✅ `face_recognition` library for identifying known individuals  
✅ Supports both **live webcam** and **static image** input  
✅ Saves processed images with bounding boxes and labels  
✅ Generates `.txt` files with detailed analysis per face  
✅ Fully compatible with Python 3.10+

---

## 🖥️ How to Run (Verified Setup)

### 1. Clone the Repository

```bash
git clone https://github.com/ROBIN-M-P/MyRealtimeFaceApp.git
cd MyRealtimeFaceApp
```

### 2. Prepare Known Faces Data

Place your known face images inside the `data/known_faces/` directory.

```
MyRealtimeFaceApp/
└── data/
    └── known_faces/
        ├── face1.png
        └── robin.jpg
```

**Recommendations:**
- Use `.jpg` or `.png` files
- Avoid spaces or special characters in filenames

```bash
mkdir -p data/known_faces
mv /path/to/your/image.png data/known_faces/my_face.png
```

### 3. Install Dependencies

Ensure Python 3.10+ is installed. Then:

```bash
python3 -m venv .venv        # Create virtual environment
source .venv/bin/activate    # On Linux/macOS
# On Windows:
# .venv\Scripts\activate

pip install --upgrade pip
pip install -r requirements.txt
```

ℹ️ DeepFace models will be downloaded automatically on first run.

### 4. Run the Application

#### A. 🖼️ Static Image Processing (Recommended for Codespaces)

```bash
mkdir -p output_faces
python -m src.main_detector
```

Or process a specific image:

```bash
python -m src.main_detector --input image --path_im data/known_faces/your_image.png
```

**Output:**  
- `output_faces/<image_name>_processed.png`  
- `output_faces/<image_name>_analysis.txt`  

You can download these from your file explorer (e.g., in GitHub Codespaces).

#### B. 🎥 Live Webcam (Requires Local Machine)

**Prerequisite:** Local machine with a display + webcam.

**Steps:**
- Edit `src/main_detector.py`
- Ensure this line is active:
```python
type_input = args['input']
```
- Uncomment these lines inside the webcam block:
```python
cv2.namedWindow
cv2.imshow
cv2.waitKey
cv2.putText
cv2.destroyAllWindows
```
Then run:

```bash
python -m src.main_detector --input webcam
```

Press `q` to quit the display window.

---

## 📂 Project Structure

```
MyRealtimeFaceApp/
├── data/
│   └── known_faces/
├── models/
│   └── emotion_model.hdf5
├── output_faces/
│   └── face1_processed.png
│   └── face1_analysis.txt
├── src/
│   ├── config.py
│   ├── f_Face_info.py
│   ├── face_recognition_core.py
│   ├── face_recognition_main.py
│   ├── face_recognition_storage.py
│   └── main_detector.py
├── requirements.txt
└── README.md
```

---

## 📘 Troubleshooting Guide

### ❗ Large Model Files (Git LFS)

DeepFace models like `emotion_model.hdf5` are large. For larger setups, consider using Git LFS.

```bash
sudo apt install -y git-lfs
git lfs install
git lfs pull
```

### ⚠️ Common Errors & Fixes

**`IndentationError: unexpected indent`**  
Cause: Extra spaces or tabs in code.  
Fix: Open in VS Code and correct spacing.

**`FileNotFoundError: .../known_faces/`**  
Cause: Missing directory or bad filenames.  
Fix:
- Ensure `data/known_faces/` exists
- Use proper image extensions
- Avoid special characters in names

**`qt.qpa.xcb` / `Camera index out of range`**  
Cause: Running webcam mode in a headless system.  
Fix: Use image mode in Codespaces. Use webcam only locally.

---

## 👨‍💻 Author

**ROBIN M P**  
📍 Bangalore, India  
📧 robinpyromp@gmail.com  
🔗 [GitHub Profile](https://github.com/ROBIN-M-P)
