# Computer Vision – CA4 (HW4): Advanced Image Processing and Analysis

This folder contains **Homework 4 (CA4 / HW4)** for the **Computer Vision** course.  
The assignment is implemented in a Jupyter Notebook and follows the tasks described in the provided **Instruction.pdf**. The focus of this homework is on **more advanced image processing and analysis techniques**, building on the previous assignments.

---

## Repository Structure

```
CA4/
├── CV_HW4_810101514_810101490.ipynb   # Main notebook (assignment text + full implementation)
├── Instruction.pdf                   # Official homework instructions
└── README.md                         # This file
```

---

## How to Run

1. Open the notebook:
```bash
jupyter notebook CV_HW4_810101514_810101490.ipynb
```
2. Run the cells **top-to-bottom** to reproduce all results, figures, and analyses.

### Requirements

Typical Python packages used:

- `numpy`
- `opencv-python`
- `matplotlib`
- `scikit-image`
- `scipy` (if required by some parts)

Example installation:
```bash
pip install numpy opencv-python matplotlib scikit-image scipy
```

---

## Assignment Goal (as described in the instructions and notebook)

The main goal of this homework is to **apply and analyze advanced computer vision techniques** on given images.  
Compared to previous assignments, this homework emphasizes:

- Deeper analysis of image features and structures
- More complex processing pipelines
- Careful visualization and interpretation of results
- Understanding the limitations and behavior of different methods

This is a **classical computer vision** assignment and focuses on algorithmic and analytical methods rather than deep learning.

---

## Notebook Structure and Tasks

### 1. Loading and Inspecting the Data

- The notebook starts by loading the required images or datasets as specified in `Instruction.pdf`.
- Basic inspection is performed:
  - Image dimensions and formats
  - Color vs grayscale representation
- Visualization utilities are defined to display intermediate and final results.

---

### 2. Preprocessing

Depending on the task, preprocessing steps may include:

- Grayscale conversion
- Noise reduction (smoothing filters)
- Normalization or contrast enhancement
- Resizing or cropping (if required)

The goal is to prepare the data for the main processing stages in a stable and consistent way.

---

### 3. Core Processing Tasks

This section implements the **main required algorithms** described in the homework instructions. Depending on the exact question parts in the notebook, this can include:

- Filtering and kernel-based operations
- Edge or structure detection
- Region-based or feature-based analysis
- Geometric or morphological transformations
- Measurement and comparison of image properties

Each step is:
- Implemented in code
- Visualized
- Explained in the notebook

---

### 4. Parameter Analysis and Experiments

The notebook performs experiments with different parameters, such as:

- Kernel sizes
- Threshold values
- Iteration counts
- Scale or resolution changes

The effects of these parameters on the output are:

- Visually compared
- Discussed in text
- Interpreted in terms of algorithm behavior

---

### 5. Visualization of Results

- Intermediate and final outputs are plotted using `matplotlib` or OpenCV utilities.
- Comparisons between different methods or parameter settings are shown side-by-side.
- This qualitative analysis is an important part of the homework evaluation.

---

### 6. Analysis and Discussion

The final part of the notebook includes discussion of:

- What works well and why
- Where the methods fail or produce artifacts
- Sensitivity to noise, parameters, or image content
- Strengths and weaknesses of the applied techniques

---

## Results and Observations

From the experiments in the notebook, the following types of conclusions are drawn:

- Proper preprocessing has a strong impact on the final results.
- Parameter selection is critical for stable and meaningful outputs.
- Different methods emphasize different aspects of the image (edges, regions, textures, etc.).
- Visual inspection is essential to understand both successes and failure cases.

All these observations are supported by figures and outputs shown in the notebook.

---

## Educational Goals

This homework is designed to help students:

- Practice building **multi-step image processing pipelines**
- Develop intuition about **algorithm behavior and parameters**
- Improve skills in **visual analysis and result interpretation**
- Gain experience with more advanced classical computer vision techniques

---

## Notes

- All figures and intermediate results are generated inside the notebook.
- The implementation follows the instructions provided in `Instruction.pdf`.
- The project is intended for **academic and educational use**.
