# 🎯 Real-time Face Attribute Detection – Project Setup Guide

This guide outlines the complete setup and execution process for the **Real-time Face Attribute Detection** project. It includes cloning the repository, setting up a Conda environment, installing dependencies, and running the application in both static and live webcam modes.

---

## 📦 1. Clone the Repository

Clone the project repository from GitHub to your desired local directory:

```bash
git clone https://github.com/ROBIN-M-P/Real-time-Face-Attribute-Detection-project-CLEAN "Your/Desired/Local/Path"
```

---

## 📂 2. Navigate to the Project Directory

```bash
cd "Your/Desired/Local/Path/project_repo-clone"
```

---

## 🧾 3. Verify Project Contents

```bash
dir
git status
```

Expected files/folders:
- `.gitignore`
- `data/`
- `models/`
- `README.md`
- `requirements.txt`
- `src/`

---

## 🐍 4. Set Up Conda Environment

```bash
conda create -n my_face_app_env python=3.10
```

---

## 🔁 5. Activate the Environment

```bash
conda activate my_face_app_env
```

---

## 🔧 6. Upgrade pip

```bash
C:\Users\lenovo\miniconda3\envs\my_face_app_env\python.exe -m pip install --upgrade pip
```

> 📝 Note: Adjust the path as per your Conda installation.

---

## 📚 7. Install Dependencies

```bash
pip install -r requirements.txt
```

Key libraries:
- `deepface`
- `dlib`
- `face-recognition`
- `opencv-python`
- `tensorflow`

---

## 🚀 8. Run the Application

Make sure you're in the project root and the environment is activated.

### 🖼️ A. Static Image Processing

```bash
mkdir -p output_faces
python -m src.main_detector
```

Or for a specific image:

```bash
python -m src.main_detector --input image --path_im data/known_faces/your_image.png
```

> Replace `your_image.png` with your image filename.

---

### 🎥 B. Live Webcam Processing

Modify `src/main_detector.py`:
- Ensure `type_input = args['input']` is active.
- Uncomment the following lines if commented:

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

> Press `q` to quit the webcam.

---

## ✅ You're All Set!

Your system is now ready to run real-time face attribute detection!

---

📁 GitHub Repo: [github.com/ROBIN-M-P/Real-time-Face-Attribute-Detection-project-CLEAN](https://github.com/ROBIN-M-P/Real-time-Face-Attribute-Detection-project-CLEAN)
