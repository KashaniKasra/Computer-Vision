# Computer Vision – HW1 (Image Processing Fundamentals)

This folder contains **Homework 1** for the **Computer Vision** course.  
The assignment is implemented in a Jupyter Notebook and focuses on **fundamental image processing operations** using a sample image and a short video, including:

- Noise modeling and denoising
- Linear and non-linear filtering
- Edge detection
- Practical experimentation with kernels and convolution
- Visual comparison and discussion of results

---

## Repository Structure

```
CA1/
├── CV-HW1-810101490-810101514.ipynb   # Main notebook (assignment + implementation)
├── Instruction.pdf                    # Official homework description
├── Pic.jpg                            # Input image used in experiments
├── Original_Vid.mp4                   # Input video (if referenced in the notebook)
└── README.md                          # This file
```

---

## How to Run

1. Open the notebook:
```bash
jupyter notebook CV-HW1-810101490-810101514.ipynb
```
2. Run the cells **top-to-bottom** to reproduce all results and figures.

### Requirements
Typical packages used:
- `numpy`
- `opencv-python`
- `matplotlib`
- `scipy` (if used for filtering)
- `skimage` (optional)

Example:
```bash
pip install numpy opencv-python matplotlib scipy scikit-image
```

---

## Notebook Structure (as in the file)

### Imports
The notebook starts by importing the required libraries for:
- Image I/O and display
- Numerical processing
- Filtering and edge detection
- Plotting and visualization

---

## Section 1

This section introduces the input data and basic setup used throughout the assignment.

Typical steps include:
- Loading the input image (`Pic.jpg`)
- Displaying and inspecting basic properties (shape, type, etc.)
- Preparing helper functions for visualization and processing

---

## Section 2 – Core Image Processing Tasks

This is the main part of the homework and contains the following required tasks (exactly as stated in the notebook):

### 1) Loading the image again
The image is reloaded to ensure a clean baseline for subsequent experiments and comparisons.

### 2) Adding *Salt and Pepper Noise* to the original image
- Artificial impulse noise is added to the image.
- The noisy image is visualized and compared to the original.
- The goal is to simulate common real-world noise and prepare for denoising experiments.

### 3) Explaining kernels in image processing and their applications
This section provides a conceptual explanation of:
- What a **kernel (filter mask)** is
- How convolution works
- Common applications such as:
  - Smoothing / blurring
  - Sharpening
  - Edge detection
  - Noise reduction

It also explains different ways kernels can be applied to images (spatial filtering, convolution, etc.).

### 4) Applying *Mean Filter*, *Gaussian Filter*, and *Median Filter* on the original image
In this step, three different filters are implemented and applied:

- **Mean Filter (Averaging Filter)**:
  - Linear filter
  - Reduces noise but blurs edges

- **Gaussian Filter**:
  - Linear, weighted smoothing
  - Better edge preservation than mean filter
  - Controlled by kernel size and sigma

- **Median Filter**:
  - Non-linear filter
  - Very effective against salt-and-pepper noise
  - Preserves edges better than linear smoothing filters

The outputs of all three filters are displayed and compared visually.

### 5) Applying the best filter on the salt-and-pepper noisy image
- Based on the previous comparison, the **most suitable filter** is chosen (typically the median filter for impulse noise).
- The selected filter is applied to the noisy image.
- The denoised result is compared to:
  - The original clean image
  - The noisy image
- The effectiveness of the filter is discussed.

### 6) Applying *Sobel*, *Laplacian*, and *Canny* filters (edge detectors) on the original image
This part focuses on **edge detection** using three classic methods:

- **Sobel Filter**:
  - First-order derivative operator
  - Detects horizontal and vertical edges
  - Produces gradient magnitude images

- **Laplacian Filter**:
  - Second-order derivative operator
  - Highlights regions of rapid intensity change
  - More sensitive to noise

- **Canny Edge Detector**:
  - Multi-stage edge detection algorithm
  - Includes smoothing, gradient computation, non-maximum suppression, and hysteresis thresholding
  - Produces clean and well-localized edges

The results of all three methods are shown and compared.

---

## Section 3

This section typically contains:
- Additional experiments (if any)
- Further analysis or discussion
- Visual comparisons and conclusions drawn from the previous steps

---

## Results and Observations

From the experiments in the notebook, the following general observations are discussed:

- **Median filtering** is the most effective for removing salt-and-pepper noise.
- **Gaussian filtering** provides smoother results but can blur edges.
- **Mean filtering** is simple but less robust for impulse noise.
- For edge detection:
  - Sobel is simple and fast but less precise.
  - Laplacian is more sensitive to noise.
  - Canny provides the best edge maps due to its multi-stage design.

All these observations are supported by visual results shown in the notebook.

---

## Educational Goals

This homework is designed to help students:

- Understand spatial filtering and kernels
- Learn the difference between linear and non-linear filters
- Gain intuition about noise and denoising techniques
- Practice edge detection methods
- Develop the habit of **visual analysis and comparison** in computer vision

---

## Notes

- All figures and outputs are generated inside the notebook.
- The implementation follows the instructions provided in `Instruction.pdf`.
- The project is intended for **academic and educational use**.
