# Computer Vision – CA2 (HW2): CAPTCHA Segmentation and Recognition

This folder contains **Homework 2 (CA2 / HW2)** for the **Computer Vision** course.  
The assignment focuses on **image processing and classical computer vision techniques** for solving a practical problem: **segmenting and analyzing CAPTCHA images**.

---

## Repository Structure

```
CA2/
├── CV-HW2-810101490-810101514.ipynb   # Main notebook (assignment + full implementation)
├── Instruction.pdf                    # Official homework description
├── Mapset/                            # Dataset used in the assignment
├── Captcha_segmented/                 # Output segmented CAPTCHA characters
├── captcha_results.csv                # Quantitative results / logs
└── README.md                          # This file
```

---

## How to Run

1. Open the notebook:
```bash
jupyter notebook CV-HW2-810101490-810101514.ipynb
```
2. Run the cells **top-to-bottom** to reproduce all experiments, figures, and result files.

### Requirements

Typical Python packages used in this notebook:

- `numpy`
- `opencv-python`
- `matplotlib`
- `scikit-image`
- `scikit-learn`
- `pandas`

Example installation:
```bash
pip install numpy opencv-python matplotlib scikit-image scikit-learn pandas
```

---

## Assignment Goal (as stated in the HW description)

The main goal of this homework is to **design a complete pipeline for processing CAPTCHA images**, including:

- Preprocessing and noise removal
- Image binarization and morphological operations
- Character segmentation
- Feature extraction (if applicable)
- Evaluation of segmentation / recognition quality
- Analysis of failure cases

This is a **classical computer vision** problem that emphasizes **image processing and geometry**, not deep learning.

---

## Notebook Structure and Tasks

### 1. Loading and Inspecting the Dataset

- The CAPTCHA images are loaded from the `Mapset/` directory.
- Basic inspection is performed:
  - Image size
  - Color / grayscale format
  - Typical noise patterns and distortions
- Visualization utilities are defined to display intermediate results.

---

### 2. Preprocessing

In this section, the notebook applies a sequence of preprocessing steps such as:

- Converting images to grayscale
- Noise reduction using smoothing filters
- Contrast enhancement (if needed)
- Thresholding / binarization

The goal is to produce a **clean binary image** that makes character boundaries more separable.

---

### 3. Morphological Operations

To improve segmentation quality, the following operations are typically applied:

- Erosion and dilation
- Opening and closing
- Removal of small connected components (noise)
- Filling holes inside characters

These steps help:
- Separate touching characters
- Remove spurious blobs
- Improve the shape of character regions

---

### 4. Character Segmentation

This is the core part of the homework.

The notebook performs:

- Connected component analysis or contour detection
- Bounding box extraction for each character
- Sorting characters from left to right
- Cropping and saving each character image into `Captcha_segmented/`

Each CAPTCHA image is thus decomposed into **individual character images**.

---

### 5. Post-processing and Filtering

After initial segmentation:

- Very small or very large components are filtered out
- Bounding boxes are refined
- Overlapping or incorrectly split components are handled (when possible)

The goal is to maximize **correct character isolation**.

---

### 6. Feature Extraction and Recognition

Depending on the exact HW instructions, this part may include:

- Extracting simple features (e.g., pixel-based, shape-based)
- Applying a simple classifier (e.g., k-NN, SVM)
- Or only evaluating segmentation quality without full recognition

All steps and results are documented in the notebook.

---

### 7. Evaluation and Results

The notebook produces:

- Visual results of segmented characters
- Quantitative logs saved in `captcha_results.csv`
- Analysis of:
  - Successful segmentations
  - Typical failure cases
  - Reasons for errors (over-segmentation, under-segmentation, noise, touching characters, etc.)

---

## Results and Observations

From the experiments, the following general conclusions are discussed:

- Proper preprocessing and morphological operations are **crucial** for good segmentation.
- Simple thresholding is often not enough for noisy CAPTCHAs.
- Character touching and distortion remain the main sources of error.
- Classical CV methods can achieve reasonable performance, but are sensitive to parameter choices.

All these observations are supported by the visual and numerical results shown in the notebook.

---

## Educational Goals

This homework is designed to help students:

- Practice building a **complete image processing pipeline**
- Understand the role of preprocessing in real-world vision tasks
- Learn how to use morphological operations effectively
- Gain experience with **connected components and segmentation**
- Analyze and debug failure cases in vision systems

---

## Notes

- All figures and intermediate results are generated inside the notebook.
- The implementation follows the instructions provided in `Instruction.pdf`.
- Output segmented characters are stored in `Captcha_segmented/`.
- The project is intended for **academic and educational use**.
