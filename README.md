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

The assignment uses PyTorch for the R2D2-based feature extraction and matching pipeline.

Install the CUDA 12.8 compatible PyTorch packages using:

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

If CUDA is not available, the notebook can still be executed using the CPU, although R2D2 processing may take considerably longer.

---