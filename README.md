# CV5570 - Computer Vision for Construction Engineering

## Assignment 2

### Student Details

* **Name:** Vasantharan K
* **Roll No:** ID26S012
* **Program:** M.S
* **Department:** School of Interdisciplinary Studies
* **Course:** CV5570 - Computer Vision for Construction Engineering
* **Semester:** Jul - Nov 2026

--- 

## Project Structure

```text
CV5570_Assignment_2/
│
├── env/                    # Python virtual environment
├── dataset/                # Dataset used for the assignment
├── notebook_results/       # Results generated from the notebook
├── splits/                 # Train/validation/test dataset splits
├── checkpoints/            # Trained model weights and checkpoints
├── report/                 # Assignment report
│
├── Assignment_2.ipynb      # Main assignment notebook
├── README.md               # Project documentation
├── requirements.txt        # Python dependencies
└── .gitignore              # Git ignore configuration
```

---

# Setup and Execution

## Step 1 - Clone / Open the Project

Open a terminal and navigate to the project directory:

```bash
cd CV5570_Assignment_2
```

---

## Step 2 - Create a Virtual Environment

Create a Python virtual environment named `env`:

```bash
python -m venv env
```

If the virtual environment already exists, this step can be skipped.

---

## Step 3 - Activate the Virtual Environment

### Windows PowerShell

```powershell
.\env\Scripts\Activate
```

### Windows Command Prompt

```cmd
env\Scripts\activate
```

After activation, the terminal should show `(env)` at the beginning of the command prompt.

---

## Step 4 - Upgrade pip

It is recommended to upgrade `pip` before installing the dependencies:

```bash
python -m pip install --upgrade pip
```

---

## Step 5 - Install Required Packages

Install the packages listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

---

## Step 6 - Install PyTorch with CUDA Support

The assignment uses PyTorch for training and inference with the deep learning-based object detection models.

Install the CUDA 13.0 compatible PyTorch packages using:

```bash
python -m pip uninstall torch torchvision torchaudio -y
python -m pip install torch torchvision --index-url https://download.pytorch.org/whl/cu130
```

### Verify PyTorch Installation

Run:

```bash
python -c "import torch; print('PyTorch:', torch.__version__); print('CUDA available:', torch.cuda.is_available()); print('CUDA version:', torch.version.cuda)"
```

If CUDA is available, the output should contain:

```text
CUDA available: True
```

If CUDA is not available, the notebook can still be executed using the CPU but it consumes more time for training.

---

---

**# Step 7 - Install Jupyter Notebook**

If Jupyter Notebook is not already installed through `requirements.txt`, install it using:

```bash
pip install notebook
```

Alternatively, JupyterLab can be installed with:

```bash
pip install jupyterlab
```

---

**# Step 8 - Launch the Notebook**

Make sure the terminal is inside the project directory:

```bash
cd CV5570_Assignment_2
```

Then start Jupyter Notebook:

```bash
jupyter notebook
```

A browser window should open automatically.

Open:

```text
Assignment_2.ipynb
```

---

**# Step 9 - Select the Correct Python Kernel**

Inside Jupyter Notebook, select the Python interpreter corresponding to the virtual environment:

```text
env
```

For example:

```text
Kernel → Change Kernel → Python (env)
```

This is important because all packages installed in the virtual environment must be accessible to the notebook.

---

**# Step 10 - Run the Notebook**

Run the notebook from the **first cell to the last cell in sequential order**.

In Jupyter Notebook, use:

```text
Kernel → Restart Kernel and Run All Cells
```

or run individual cells using:

```text
Shift + Enter
```

The notebook performs object detection experiments using three different approaches:

1. **Two-Stage Object Detection – Faster R-CNN**
2. **One-Stage Object Detection – YOLO**
3. **Transformer-Based Object Detection – DETR**

The notebook generates predictions, visualizations, evaluation results, and comparative results for the three approaches.

---

# Dataset

The dataset used for Assignment 2 is stored in:

```text
dataset/
```

The dataset contains the images and corresponding annotation information required for training and evaluating the object detection models.

The dataset directory should remain in its original location so that the relative paths used by the notebook remain valid.

---

# Dataset Splits

The training, validation, and testing splits are stored in:

```text
splits/
```

The split information is used to ensure consistent training, validation, and testing across the different object detection models.

The same dataset split should be maintained when comparing the performance of the different detection approaches.

---

# Model Checkpoints

Trained model weights and checkpoints are stored in:

```text
checkpoints/
```

These files may include the saved weights generated during model training and can be used for evaluation or inference without retraining the models.

Due to the potentially large size of trained model files, the availability of individual checkpoint files may depend on the project distribution.

---

# Results

Results generated during notebook execution are stored in:

```text
notebook_results/
```

The directory contains the output visualizations, prediction results, evaluation results, and other intermediate outputs generated during the experiments.

The final assignment report is available in:

```text
report/
```

---

# Object Detection Models

Assignment 2 evaluates three different object detection approaches.

## Faster R-CNN

Faster R-CNN is used as the **two-stage object detection** approach.

The model first generates region proposals and then performs classification and bounding-box regression for the detected regions.

---

## YOLO

YOLO is used as the **one-stage object detection** approach.

YOLO performs object localization and classification in a single detection pipeline, providing an efficient approach for object detection.

---

## DETR

DETR (Detection Transformer) is used as the **transformer-based object detection** approach.

DETR formulates object detection as a direct set-prediction problem and uses a Transformer architecture for object detection.

---

# GPU Support

GPU acceleration is recommended for training and inference, particularly for the deep learning-based object detection models.

To check whether PyTorch can access the GPU:

```bash
python -c "import torch; print(torch.cuda.is_available())"
```

For additional information:

```bash
python -c "import torch; print(torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'CUDA GPU not available')"
```

If a CUDA-enabled GPU is detected, PyTorch can use GPU acceleration for model training and inference.

If CUDA is unavailable, the notebook can still be executed using the CPU, although training and inference may take considerably longer.

---

# Re-running the Assignment

To run the assignment from a clean environment:

```bash
cd CV5570_Assignment_2

python -m venv env

.\env\Scripts\Activate

python -m pip install --upgrade pip

pip install -r requirements.txt

python -m pip uninstall torch torchvision torchaudio -y

python -m pip install torch torchvision --index-url https://download.pytorch.org/whl/cu130

pip install notebook

jupyter notebook
```

Then open:

```text
Assignment_2.ipynb
```

and run all cells sequentially.

---

# Important Notes

1. **Activate the virtual environment before running the notebook.**

2. Ensure that the notebook is using the **`env` Python kernel**.

3. Keep the `dataset/`, `splits/`, `checkpoints/`, and `notebook_results/` directories in their original locations.

4. Run notebook cells **in sequential order** because later cells may depend on variables, models, or results generated by earlier cells.

5. A CUDA-enabled GPU is recommended for faster model training and inference.

6. If CUDA is unavailable, the notebook can be executed on the CPU, but processing and training time may increase significantly.

7. Do not rename or move the dataset, annotation, split, or checkpoint files unless the corresponding paths in the notebook are updated.

8. Ensure sufficient disk space and system memory are available when training and saving model checkpoints.

9. The object detection models should be evaluated using the same test split to ensure a fair comparison.

---

# Assignment Notebook

Main notebook:

```text
Assignment_2.ipynb
```

The notebook contains the complete implementation, training and evaluation procedures, experiments, visualizations, and comparative analysis for Assignment 2.

---

# Assignment Report

The final assignment report is available in:

```text
report/
```

The report documents the dataset, preprocessing, object detection methods, experimental setup, results, limitations, comparison, and conclusions.

---

# Project Repository

The complete project source code, notebook, documentation, and related files are maintained in the GitHub repository:

```text
https://github.com/vasantharan/CV5570_Assignment_2
```

---

# Assignment Workflow

The overall workflow followed in this assignment is:

```text
Dataset
   │
   ▼
Dataset Acquisition and Preprocessing
   │
   ▼
Train / Validation / Test Split
   │
   ├───────────────┬────────────────┐
   ▼               ▼                ▼
Faster R-CNN      YOLO             DETR
(Two-Stage)      (One-Stage)      (Transformer)
   │               │                │
   └───────────────┴────────────────┘
                   │
                   ▼
             Model Evaluation
                   │
                   ▼
          Experimental Comparison
                   │
                   ▼
              Final Report
```

---

# End of README

This repository contains the implementation and experimental results for **CV5570 – Computer Vision for Construction Engineering, Assignment 2**.