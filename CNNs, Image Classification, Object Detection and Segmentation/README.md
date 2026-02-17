# Computer Vision – CA3 (HW3): Feature Detection, Matching, and Image Analysis

This folder contains **Homework 3 (CA3 / HW3)** for the **Computer Vision** course.  
The assignment is implemented in a Jupyter Notebook and focuses on **classical feature-based computer vision pipelines**, including:

- Loading and analyzing images
- Detecting interest points / keypoints
- Extracting local descriptors
- Matching features between images
- Visualizing correspondences and analyzing results

---

## Repository Structure

```
CA3/
├── CV-HW3-810101490-810101514.ipynb   # Main notebook (assignment text + full implementation)
├── Instruction.pdf                   # Official homework instructions
├── images/                           # Input images used in experiments
└── README.md                         # This file
```

---

## How to Run

1. Open the notebook:
```bash
jupyter notebook CV-HW3-810101490-810101514.ipynb
```
2. Run the cells **top-to-bottom** to reproduce all figures, matches, and visualizations.

### Requirements

Typical Python packages used:

- `numpy`
- `opencv-python`
- `matplotlib`
- `scikit-image`
- `scipy` (if required by some steps)

Example:
```bash
pip install numpy opencv-python matplotlib scikit-image scipy
```

---

## Assignment Goal (as described in the instructions and notebook)

The main goal of this homework is to **build and analyze a feature-based vision pipeline** for comparing images.  
The tasks emphasize:

- Understanding **keypoints / interest points**
- Understanding **local descriptors**
- Performing **feature matching**
- Visualizing and analyzing correspondences
- Discussing strengths and weaknesses of different choices

This is a **classical computer vision** assignment (no deep learning), focused on geometry, descriptors, and matching.

---

## Notebook Structure and Tasks

### 1. Loading and Inspecting Images

- Images are loaded from the `images/` directory.
- Basic inspection is performed:
  - Image size and format
  - Color vs grayscale
- Helper visualization functions are defined to display results clearly.

---

### 2. Preprocessing

Depending on the task, the notebook may apply:

- Conversion to grayscale
- Smoothing or normalization
- Contrast adjustment

The goal is to prepare images for **stable feature detection**.

---

### 3. Feature / Keypoint Detection

In this part, the notebook detects interest points using classical methods (as required by the HW), such as:

- Corner detectors or blob detectors
- Or standard OpenCV feature detectors (e.g., SIFT/ORB/SURF, depending on availability and instructions)

For each image, the following are visualized:

- Detected keypoints
- Their spatial distribution
- The effect of detector parameters

---

### 4. Descriptor Extraction

For each detected keypoint:

- A local descriptor is computed
- Descriptors encode the local appearance around each keypoint
- The notebook explains and demonstrates how descriptors are represented and stored

These descriptors are later used for matching between images.

---

### 5. Feature Matching

The notebook then performs **pairwise matching** between images:

- A distance metric (e.g., L2 or Hamming) is used
- Nearest-neighbor or ratio-test matching is applied
- Bad / ambiguous matches are filtered out

The result is a set of **corresponding keypoints** between two images.

---

### 6. Visualization of Matches

- Matches are drawn using lines between corresponding points
- Good and bad matches are visually inspected
- The notebook shows how different thresholds or parameters affect match quality

This step is crucial for **qualitative evaluation**.

---

### 7. Analysis and Discussion

The notebook includes discussion of:

- How many matches are obtained
- Where matches succeed or fail
- Sensitivity to:
  - Image changes (scale, rotation, viewpoint, illumination)
  - Noise and blur
- Limitations of classical feature-based methods

---

## Results and Observations

From the experiments, the following general observations are discussed:

- Good feature detectors produce **repeatable and well-distributed keypoints**.
- Descriptor choice strongly affects matching quality.
- Simple nearest-neighbor matching often produces outliers, so **filtering (e.g., ratio test)** is important.
- Visual inspection is essential to understand **failure cases** such as:
  - Repetitive patterns
  - Low-texture regions
  - Large viewpoint changes

All these points are supported by the figures and outputs shown in the notebook.

---

## Educational Goals

This homework is designed to help students:

- Understand the **feature-based vision pipeline**
- Learn how detectors and descriptors work together
- Gain experience with **feature matching and evaluation**
- Practice visual analysis of computer vision results
- Build intuition about the strengths and weaknesses of classical methods

---

## Notes

- All figures and intermediate results are generated inside the notebook.
- The implementation follows the instructions provided in `Instruction.pdf`.
- The project is intended for **academic and educational use**.
