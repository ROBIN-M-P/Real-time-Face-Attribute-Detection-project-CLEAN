Project Setup Guide
This document summarizes the steps taken to set up a Python project from a Git repository, including environment management with Conda and dependency installation.

1. Repository Cloning
The project repository was successfully cloned from its remote GitHub source to a specified local directory.

Command Used:
git clone https://github.com/ROBIN-M-P/Real-time-Face-Attribute-Detection-project-CLEAN "Your/Desired/Local/Path"

Note: The actual 46.90 MiB of data was received.
2. Navigate to Project Directory
After cloning, the working directory was changed to the newly created project folder.

Command Used:
cd "Your/Desired/Local/Path/project_repo-clone"
3. Verify Project Contents and Git Status
The contents of the cloned repository were inspected, and the Git status was checked to ensure the local copy was up-to-date.

Commands Used:
dir
git status

Output confirmed the presence of key project files (.gitignore, data, models, README.md, requirements.txt, src) and a clean working tree.
4. Conda Environment Setup
A new, isolated Conda environment was created specifically for this project to manage its Python version and dependencies.

Command Used:
conda create -n my_face_app_env python=3.10
5. Activate Conda Environment
The newly created Conda environment was activated to ensure all subsequent Python commands operate within this isolated environment.

Command Used:
conda activate my_face_app_env

Prompt changed from (base) to (my_face_app_env).
6. Update Pip (within environment)
The pip package installer within the activated Conda environment was updated to its latest version. This ensures compatibility and resolves potential installation issues.

Command Used:
C:\Users\lenovo\miniconda3\envs\my_face_app_env\python.exe -m pip install --upgrade pip

Note: The specific path to the environment's Python executable was used as recommended by Conda.
7. Install Project Dependencies
All required Python libraries and packages for the project, as specified in requirements.txt, were installed into the my_face_app_env environment.

Command Used:
pip install -r requirements.txt

Installation successful, including packages like deepface, dlib, face-recognition, opencv-python, and tensorflow.
8. Run the Application
With all dependencies installed, the project is now ready to be run. Ensure you are in the project's root directory (Your/Desired/Local/Path/project_repo-clone) and your my_face_app_env Conda environment is activated.

•	A. Static Image Processing
This mode processes individual image files and saves both visual and textual analysis outputs.

To run the application for static image processing:

mkdir -p output_faces
python -m src.main_detector

Or, to process a specific image:

python -m src.main_detector --input image --path_im data/known_faces/your_image.png

Note: Replace your_image.png with the actual path to your image. Processed images and analysis .txt files will be saved in the output_faces/ directory.
•	B. Live Webcam Processing
This mode processes real-time video streams from your webcam.

Prerequisite: A local machine with a display and webcam.

Steps:

Edit src/main_detector.py:

Ensure this line is active: type_input = args['input']

Uncomment these lines inside the webcam block (remove the # at the beginning of each line if present):

cv2.namedWindow
cv2.imshow
cv2.waitKey
cv2.putText
cv2.destroyAllWindows

To run the application for live webcam processing:

python -m src.main_detector --input webcam

Press q to quit the display window.
Next Steps
Refer to the original README.md within your cloned repository for more detailed instructions on project usage and troubleshooting.
