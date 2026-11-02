# AI Application Exploration (SOFT 215)

This repository contains five Jupyter notebooks exploring neural networks, computer vision, and model evaluation.

## Notebooks

| Notebook | Description |
|---|---|
| [perceptron_lab.ipynb](./perceptron_lab.ipynb) | Implements a basic perceptron and step activation function, then explains how inputs and weights affect its output. |
| [fashion_mnist_neural_network.ipynb](./fashion_mnist_neural_network.ipynb) | Trains and evaluates a neural network that classifies FashionMNIST clothing images. |
| [CIFAR_10_CCN_Assignment.ipynb](./CIFAR_10_CCN_Assignment.ipynb) | Builds and trains a convolutional neural network on CIFAR-10, plots training loss, evaluates test accuracy, and displays predictions. |
| [model_performance_assignment.ipynb](./model_performance_assignment.ipynb) | Compares two PyTorch classifiers on scikit-learn's breast cancer dataset using validation metrics and error analysis. |
| [ai_application_exploration.ipynb](./ai_application_exploration.ipynb) | Uses a pretrained ResNet-18 image-classification model to explore predictions for an image. |

## Requirements

- Python 3.12 (the notebooks were developed with Python 3.12.10).
- Packages in [requirements.txt](./requirements.txt), including PyTorch, torchvision, NumPy, scikit-learn, Matplotlib, Pillow, IPython, ipykernel, and Jupyter Notebook.

## Setup (Windows PowerShell)

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

If PowerShell blocks the activation script, run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` first.

## Run a notebook

**In VS Code:**

1. Open the notebook you want to run.
2. Select the `.venv` Python 3.12 kernel.
3. Choose **Run All**.

**From the command line:**

```powershell
python -m jupyter notebook
```

Open the notebook from the Jupyter file browser and choose **Run > Run All Cells**.

## Data and execution notes

- CIFAR-10 and FashionMNIST are downloaded by torchvision the first time their notebooks run.
- The ResNet-18 notebook downloads pretrained weights on first use. `Cat03.jpg` is included in the repository; the notebook can also download the image if it is missing.
- The model-performance notebook uses the breast cancer dataset included with scikit-learn and does not need a separate dataset download.
- The notebooks select a GPU when one is available through the installed PyTorch build and otherwise use the CPU. Training time varies with hardware.
- Model training results may vary slightly across machines and PyTorch versions. The model-performance notebook includes recorded comparison and error-analysis results; update those Markdown cells if a new run produces different metrics.
