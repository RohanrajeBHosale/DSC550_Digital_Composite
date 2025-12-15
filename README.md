# DSC550_Digital_Composite --- Sketch Studio: AI Sketch-to-Portrait Generator

 Sketch Studio: Bring drawings to life! An interactive Python tool utilizing ControlNet Lineart for structural fidelity and BLIP for semantic understanding. Features a GUI for real-time attribute customization (hair, eyes, gender) and 8k realistic rendering.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/[YOUR_USERNAME]/[YOUR_REPO]/blob/main/notebooks/Final_Lineart_Studio.ipynb)
![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)
![License MIT](https://img.shields.io/badge/license-MIT-green.svg)
![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97-HuggingFace-yellow)

**Sketch Studio** is an interactive Generative AI pipeline designed to transform rough pencil sketches into high-definition, photorealistic human portraits. By leveraging **ControlNet Lineart**, **BLIP**, and **Stable Diffusion**, it bridges the gap between analog drawing and digital rendering, respecting the structural integrity of your artwork while adding realistic textures and lighting.

---

## Examples

| Input Sketch | Intermediate (Lineart) | Final Render |
|:---:|:---:|:---:|
| *(Place `sketch.jpg` here)* | *(Place `wireframe.png` here)* | *(Place `result.png` here)* |

---

##  Features

*   **Smart Structural Analysis:** Uses **ControlNet Lineart** (not Canny or Scribble) to differentiate between structural outlines and shading noise, preventing artifacts like "wire-skin."
*   **Auto-Captioning:** Integrated **BLIP** (Bootstrapping Language-Image Pre-training) model automatically describes your sketch, saving you from writing complex prompts.
*   **Interactive Dashboard:** A user-friendly GUI built with `ipywidgets` allows you to upload images and toggle settings without touching code.
*   **Attribute Customization:** Easily override specific features via dropdowns:
    *   Gender (Man, Woman)
    *   Hair Color (Red, Blonde, Black, etc.)
    *   Eye Color
    *   Facial Hair (Beard, Clean Shaven)
*   **Smart Negative Prompting:** Automatically prevents shading from turning into beards if "Clean Shaven" is selected.

---

##  Tech Stack & Models

*   **Base Model:** [Realistic Vision V5.1](https://huggingface.co/SG161222/Realistic_Vision_V5.1_noVAE) (Stable Diffusion 1.5 fine-tune).
*   **ControlNet:** [ControlNet v1.1 Lineart](https://huggingface.co/lllyasviel/control_v11p_sd15_lineart).
*   **Captioning:** [Salesforce BLIP Large](https://huggingface.co/Salesforce/blip-image-captioning-large).
*   **Libraries:** `diffusers`, `transformers`, `controlnet_aux`, `accelerate`, `opencv-python`.

---

##  Installation

### Option 1: Google Colab (Recommended)
This pipeline requires a GPU. The easiest way to run it is via Google Colab.
1.  Click the "Open in Colab" badge at the top of this README.
2.  Change Runtime type to **T4 GPU** (or A100 if available).
3.  Run the cells sequentially.

### Option 2: Local Installation
**Prerequisites:** NVIDIA GPU with at least 8GB VRAM, Python 3.10+.

1.  Clone the repository:
    ```bash
    git clone https://github.com/[YOUR_USERNAME]/[YOUR_REPO].git
    cd [YOUR_REPO]
    ```

2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3.  Launch the notebook:
    ```bash
    jupyter notebook notebooks/Final_Lineart_Studio.ipynb
    ```

---

##  Usage Guide

1.  **Initialize Models:** Run the first 5 cells to download and load the weights into VRAM.
2.  **Launch Dashboard:** Run the cell containing the `ipywidgets` code (Cell 8).
3.  **Upload Sketch:** Click **"1. Upload & View Wireframe"**. The AI will generate a wireframe and a text caption.
4.  **Customize:** Use the dropdown menus to change hair, eyes, or skin tone.
5.  **Render:** Click **"2. Generate Final Photo"**.

---

##  Repository Structure
•	/notebooks – Final_Sketch_to_Photo.ipynb
•	/data – test_sketch.jpg, sample_output.png
•	README.md – Usage instructions.
•	requirements.txt – List of libraries (diffusers, transformers, etc.).
<img width="468" height="95" alt="image" src="https://github.com/user-attachments/assets/01391ae7-90d9-47af-9f28-ad4a012ad4e1" />


