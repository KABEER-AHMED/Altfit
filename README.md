# Altfit

Altfit is an experimental computer-vision project that uses TensorFlow Lite MoveNet pose estimation to detect human body keypoints from a webcam feed. The notebook loads a `.tflite` model, captures frames with OpenCV, runs pose inference, and draws detected skeleton keypoints/connections over the live video stream.

## Why This Is Useful

This project is useful as a starting point for fitness, posture, movement, or exercise-form analysis tools. It demonstrates:

- Running a TensorFlow Lite model locally.
- Capturing webcam frames with OpenCV.
- Resizing and preparing video frames for model inference.
- Reading MoveNet keypoint outputs.
- Drawing pose landmarks and body connections on live video.

## Project Contents

- `code_new_final.ipynb` - Main notebook for webcam-based pose estimation.
- `3.tflite` - TensorFlow Lite model file used by the notebook.
- `movenet-tflite-singlepose-lightning-v1.tar` - Archived MoveNet model artifact.
- `movenet-tflite-singlepose-lightning-v1.tar.gz` - Compressed MoveNet model artifact.
- `README.md` - Project documentation.

## Requirements

Use Python 3 with Jupyter support. Install the main dependencies with:

```bash
pip install tensorflow numpy matplotlib opencv-python jupyter
```

You also need a working webcam and permission for Python/OpenCV to access it.

## How To Use

From this folder, start Jupyter:

```bash
jupyter notebook
```

Open `code_new_final.ipynb` and run the cells in order. The notebook opens a webcam window titled `MoveNet Lightning`; press `q` while that window is focused to stop the video loop.

## Important Notes

- The notebook expects `3.tflite` to exist in the same directory.
- The drawing helper functions should be defined before the webcam loop calls them. If you run the notebook from top to bottom and encounter a `NameError`, run the helper-function cells first, then rerun the webcam loop cell.
- This repository appears to be an experimental/prototype codebase rather than a polished production application.
- Pose-estimation output is only keypoint detection; exercise classification, repetition counting, form scoring, and user feedback would need to be added separately.
- Performance depends on your local CPU/GPU, webcam quality, lighting, and TensorFlow Lite compatibility.

## Good Next Improvements

- Convert the notebook into a reusable Python script.
- Add `requirements.txt`.
- Add exercise-specific logic such as angle calculation, rep counting, and form feedback.
- Add screenshots or sample output videos.
- Document the exact MoveNet model source and version.
