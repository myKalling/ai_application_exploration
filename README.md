# Model Performance Assignment (SOFT 215)

**Assignment:** Use PyTorch and Jupyter Notebook to measure, compare, and explain the performance of neural network models.

**Notebook:** [model_performance_assignment.ipynb](./model_performance_assignment.ipynb)

## Overview

The notebook trains two simple PyTorch neural networks on the scikit-learn breast cancer dataset (569 examples, 30 input features, classes `malignant` and `benign`) and compares them on a held-out validation set.

| Step | What the notebook does |
|---|---|
| Explore data | Prints the number of examples, number of features, target classes, and examples per class |
| Prepare data | Splits features and targets, creates an 80/20 stratified train/validation split, standardizes features (scaler fit on training data only), converts to tensors, and builds `DataLoader` objects |
| Models | **Model 1**: 30 → 16 → 2 (one hidden layer). **Model 2**: 30 → 32 → 16 → 2 (two hidden layers). Both use ReLU |
| Training | 50 epochs, `CrossEntropyLoss`, Adam (learning rate 0.001), training loss printed. Validation data is never used to update weights |
| Evaluation | `model.eval()` and `torch.no_grad()`; predicted and actual classes are saved |
| Results | Accuracy, precision, recall, confusion matrix, false positives, and false negatives for each model (positive class: benign) |
| Comparison | Markdown cell answering the assignment's comparison questions |
| Error analysis | Lists five misclassified validation examples with actual and predicted classes, then a Markdown cell describing a pattern, a possible cause, and a suggested improvement |

## Requirements

- Python 3.12 (the notebook was developed with 3.12.10)
- Packages listed in [requirements.txt](./requirements.txt): `torch`, `torchvision`, `numpy`, `scikit-learn`, `matplotlib`, `Pillow`, `ipython`, `ipykernel`

The model notebook itself only needs `torch`, `numpy`, `scikit-learn`, and `ipykernel`. The remaining packages are used by the other notebooks in this repository. The dataset ships with scikit-learn, so no download is needed. The notebook runs on CPU and uses a GPU automatically if one is available.

## Setup (Windows PowerShell)

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

If PowerShell blocks the activation script, run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` first.

## Run the notebook

**In VS Code (current environment):**

1. Open `model_performance_assignment.ipynb`.
2. Select the kernel **.venv (3.12.10)** in the top-right kernel picker.
3. Choose **Run All**.

**From the command line** (requires `jupyter` or `notebook`, which are not in `requirements.txt`):

```powershell
python -m pip install notebook
python -m jupyter notebook model_performance_assignment.ipynb
```

Then choose **Run > Run All Cells**.

## Notes

- Random seeds are fixed (`RANDOM_SEED = 42`), but results can still differ slightly across machines or PyTorch versions.
- The Markdown comparison and error analysis cells contain typed numbers from the original run (both models: accuracy 0.9561, precision 0.9855, recall 0.9444, 1 false positive, 4 false negatives). If your outputs differ, update those cells to match.
