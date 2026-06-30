# Face Detection Using Viola-Jones

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green?logo=opencv&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)

## Overview

This project provides a practical implementation of face detection using the **Viola-Jones algorithm** via OpenCV. The solution offers two distinct detection modes: static image analysis and real-time video stream processing from webcam or video files. Built with Python and OpenCV, this project demonstrates fundamental computer vision techniques suitable for learning and prototyping.

**Target Users:** Students, developers, and computer vision enthusiasts seeking to understand and implement face detection algorithms.

---

## Features

### Core Detection Capabilities
- 🎯 **Static Image Detection** – Detect faces in still images with bounding box visualization
- 📹 **Real-Time Webcam Detection** – Process live video streams from webcam for instant face detection
- 📽️ **Video File Processing** – Analyze face detection in pre-recorded video files
- 🏷️ **Bounding Box Visualization** – Clear rectangular outlines around detected faces

### Algorithm & Performance
- **Viola-Jones Cascade Classifier** – Robust and efficient pre-trained model
- **Optimized Detection Parameters** – Configurable scale factor and minimum neighbors for accuracy tuning
- **Grayscale Conversion** – Optimized color space for improved detection accuracy

---

## Tech Stack

| Category | Technology |
|----------|------------|
| **Language** | Python 3.x |
| **Computer Vision** | OpenCV |
| **Algorithm** | Viola-Jones Cascade Classifier |
| **Model** | haarcascade_frontalface_default.xml |

---

## Project Structure

```
Face-Detection/
├── main.py                              # Static image face detection
├── face_detection_live.py               # Real-time webcam/video detection
├── haarcascade_frontalface_default.xml  # Pre-trained Haar Cascade model
├── test_img.jpeg                        # Sample image for testing
├── group.jpg                            # Sample group image for testing
└── README.md                            # Project documentation
```

### File Descriptions

| File | Purpose |
|------|---------|
| `main.py` | Detects faces in static images using the Haar Cascade classifier |
| `face_detection_live.py` | Performs real-time face detection from webcam or video files |
| `haarcascade_frontalface_default.xml` | Pre-trained Haar Cascade model for frontal face detection |
| `test_img.jpeg`, `group.jpg` | Sample images for testing and demonstration |

---

## Getting Started

### Prerequisites

- Python 3.6 or higher
- Webcam (for real-time detection) or video files
- Basic understanding of Python and OpenCV

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/arnavmaheshwari/Face-Detection.git
   cd Face-Detection
   ```

2. **Install dependencies:**
   ```bash
   pip install opencv-python
   ```

   Or, for a more complete OpenCV installation:
   ```bash
   pip install opencv-contrib-python
   ```

3. **Verify installation:**
   ```bash
   python -c "import cv2; print(cv2.__version__)"
   ```

---

## Usage

### Static Image Detection

Detect faces in an image file:

```bash
python main.py
```

**How it works:**
1. Loads the Haar Cascade classifier model
2. Reads `test_img.jpeg` (or modify the filename in the code)
3. Converts the image to grayscale
4. Detects faces using `detectMultiScale()`
5. Draws bounding boxes around detected faces
6. Displays the result in a window

**To use with your own image:**

Edit `main.py` and change line 6:
```python
img = cv2.imread('your_image.jpg')
```

### Real-Time Webcam Detection

Run face detection on live webcam feed:

```bash
python face_detection_live.py
```

**How it works:**
1. Initializes webcam capture with `cv2.VideoCapture(0)`
2. Processes each frame in real-time
3. Detects and highlights faces with bounding boxes
4. Displays live feed in a window
5. Press **ESC** to exit

**To use with a video file:**

Edit line 9 in `face_detection_live.py`:
```python
cap = cv2.VideoCapture('filename.mp4')
```

---

## Configuration & Tuning

The detection accuracy can be adjusted by modifying parameters in `detectMultiScale()`:

```python
faces = face_cascade.detectMultiScale(gray, 1.1, 4)
```

| Parameter | Description | Recommended Range |
|-----------|-------------|-------------------|
| `gray` | Grayscale input image | – |
| `1.1` | Scale factor (pyramid reduction) | 1.05–1.4 |
| `4` | Minimum neighbors (quality threshold) | 3–8 |

**Tuning Tips:**
- **Lower scale factor** (e.g., 1.05) → More thorough, slower detection
- **Higher scale factor** (e.g., 1.3) → Faster, fewer false positives
- **Lower minNeighbors** (e.g., 3) → More detections, more false positives
- **Higher minNeighbors** (e.g., 6) → Fewer detections, higher confidence

---

## Algorithm Overview

### Viola-Jones Cascade Classifier

The **Viola-Jones algorithm** is a landmark computer vision technique featuring:

- **Feature-Based Detection** – Uses Haar-like features for rapid face scanning
- **Integral Images** – Enables efficient feature computation
- **Cascade Classifiers** – Multi-stage pipeline for robust detection
- **Real-Time Performance** – Optimized for practical applications

The pre-trained model (`haarcascade_frontalface_default.xml`) has been trained on thousands of face and non-face images, making it suitable for frontal face detection in various lighting conditions.

---

## Performance Considerations

- **Speed:** Real-time performance on modern hardware (~30 FPS on standard webcam)
- **Accuracy:** Effective for frontal faces; less reliable for angled or partially obscured faces
- **Resource Usage:** Minimal CPU and memory footprint compared to deep learning approaches
- **Scalability:** Suitable for embedded systems and lightweight applications

**Limitations:**
- Optimized for frontal faces; reduced accuracy for profile views
- Sensitive to lighting conditions and image quality
- Potential false positives in cluttered backgrounds

---

## Extending the Project

Consider these enhancements:

- **Multiple Face Cascades** – Use eye, smile, or profile cascades for additional features
- **Deep Learning Alternative** – Integrate modern models (MTCNN, YOLOv3, etc.) for improved accuracy
- **Face Recognition** – Add identification by training on known faces
- **Filtering & Post-Processing** – Reduce false positives with morphological operations
- **Performance Metrics** – Track detection precision and recall
- **GUI Interface** – Build a user-friendly interface with settings controls
- **Batch Processing** – Process multiple images or video files sequentially
- **Database Integration** – Store detection results and metadata

---

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make your changes and test thoroughly
4. Commit with clear messages: `git commit -m "Add feature description"`
5. Push to your branch: `git push origin feature/your-feature`
6. Open a Pull Request with a detailed description

---

## License

This project is licensed under the MIT License. See the LICENSE file for details, or refer to [MIT License](https://opensource.org/licenses/MIT).

---

## Author

**Arnav Maheshwari**

- GitHub: [@arnavmaheshwari](https://github.com/arnavmaheshwari)
- Repository: [Face-Detection](https://github.com/arnavmaheshwari/Face-Detection)

---

## Acknowledgements

- **OpenCV Community** – For the powerful computer vision library
- **Viola & Jones** – Original authors of the landmark face detection algorithm
- **Haar Cascade Models** – Pre-trained classifiers provided by OpenCV

---

## Resources

- [OpenCV Official Documentation](https://docs.opencv.org/)
- [Viola-Jones Algorithm Paper](https://www.cs.cmu.edu/~efros/courses/LBMV07/Papers/viola-jones-ijcv.pdf)
- [Haar Cascades Guide](https://docs.opencv.org/master/d1/de5/classcv_1_1CascadeClassifier.html)
- [Computer Vision Tutorials](https://docs.opencv.org/master/d9/df8/tutorial_root.html)
