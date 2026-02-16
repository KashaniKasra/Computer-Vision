# Computer Vision – Final Project: Image Translation using GAN (Cityscapes)

This folder contains the **Final Project** for the **Computer Vision** course, titled **"Image Translation using GAN"**.  
The implementation is provided in a Jupyter Notebook and follows the requirements described in the accompanying **Instruction.pdf**. The project focuses on **image-to-image translation** using **Generative Adversarial Networks (GANs)**, with the **Cityscapes** dataset as the main benchmark.

---

## 📂 Repository Structure

```
Image Translation using GAN/
├── cityscapes/                         # Dataset (input/target image pairs or prepared splits)
├── CV-FinalProject-810101490-810101514.ipynb  # Main notebook (project description + full implementation)
├── Instruction.pdf                     # Official project instructions
└── README.md                           # This file
```

---

## 🚀 How to Run

1. Install dependencies (typical stack):
```bash
pip install numpy torch torchvision matplotlib opencv-python tqdm
```

2. Open the notebook:
```bash
jupyter notebook CV-FinalProject-810101490-810101514.ipynb
```

3. Run all cells **top-to-bottom** to:
- Load and preprocess the dataset
- Build the GAN models
- Train the network
- Evaluate results
- Visualize translated images

> Training can be time-consuming depending on hardware. The notebook is structured so intermediate results and checkpoints can be inspected.

---

## 🎯 Project Goal (as described in the instructions and notebook)

The main goal of this project is to implement an **image-to-image translation system** using **GANs**, where the model learns a mapping between two visual domains. In the context of Cityscapes, this typically means:

- Translating **semantic label maps → realistic street images**, or
- Translating **street images → label maps**, or
- Another paired image translation task defined in the instructions.

The project emphasizes:

- Understanding the **GAN framework**
- Implementing a **conditional GAN** (e.g., Pix2Pix-style)
- Training on **paired data**
- Evaluating results visually and qualitatively
- Analyzing strengths and limitations of the approach

---

## 🧠 Methodology and Notebook Structure

### 1. Data Loading and Preparation

- The Cityscapes dataset (or its prepared subset) is loaded from the `cityscapes/` directory.
- Images are:
  - Resized / cropped as required
  - Normalized to the appropriate range
  - Split into training and validation sets
- Paired samples (input, target) are prepared for supervised image-to-image translation.

---

### 2. Model Architecture

The notebook implements a **conditional GAN** architecture consisting of:

#### Generator
- Typically a **U-Net**-style or encoder–decoder network
- Takes an input image (e.g., label map) and produces a translated output image
- Uses skip connections (if U-Net) to preserve spatial details

#### Discriminator
- A **PatchGAN**-style discriminator (as commonly used in Pix2Pix)
- Judges whether a (input, output) pair is **real** or **fake**
- Operates on local patches to enforce high-frequency realism

---

### 3. Loss Functions

The training objective combines:

- **Adversarial Loss**:
  - Encourages the generator to produce realistic images that fool the discriminator
- **Reconstruction Loss (e.g., L1)**:
  - Encourages the generated image to be close to the ground-truth target
  - Stabilizes training and preserves structure

The total generator loss is a weighted sum of these terms, as described in the notebook.

---

### 4. Training Loop

The notebook implements the full GAN training procedure:

- For each batch:
  1. Update the **Discriminator**:
     - Maximize ability to distinguish real vs. generated pairs
  2. Update the **Generator**:
     - Minimize adversarial loss
     - Minimize reconstruction loss
- Logs:
  - Generator loss
  - Discriminator loss
- Periodically:
  - Save model checkpoints
  - Visualize generated samples for qualitative evaluation

---

### 5. Evaluation and Visualization

The notebook includes:

- Side-by-side visualization of:
  - Input image
  - Ground truth target
  - Generated output
- Qualitative comparison to assess:
  - Structural correctness
  - Visual realism
  - Artifacts or failure modes

Because image-to-image translation is largely perceptual, **visual inspection** is a key evaluation method in this project.

---

## 📊 Results and Observations

From the experiments shown in the notebook, the following types of observations are discussed:

- The model learns the **global structure** of the scene reasonably well.
- Fine details improve as training progresses, but:
  - Some textures may remain blurry
  - Some artifacts may appear in challenging regions
- The balance between adversarial loss and L1 loss strongly affects:
  - Sharpness
  - Faithfulness to the input structure
- Training stability is sensitive to:
  - Learning rate
  - Loss weights
  - Dataset size and diversity

All conclusions are supported by visual results displayed in the notebook.

---

## 🎓 Educational Objectives

This final project is designed to help students:

- Understand **GANs** and **conditional GANs** in practice
- Implement a **full deep learning pipeline** for image translation
- Work with a **real-world dataset** (Cityscapes)
- Learn how to:
  - Design models
  - Train adversarial networks
  - Debug training instability
  - Evaluate generative models qualitatively

---

## 📝 Notes

- All experiments and figures are reproducible from the notebook.
- The implementation follows the requirements stated in `Instruction.pdf`.
- This project is intended for **academic and educational use**.
- Due to the nature of GANs, results may vary depending on:
  - Random initialization
  - Training time
  - Hardware resources