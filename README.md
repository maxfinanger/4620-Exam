## Project Dependencies

This project uses the following libraries (see [`requirements.txt`](requirements.txt)):

### Core Deep Learning

- **PyTorch** (`torch`, `torchvision`) - Neural network framework & pretrained models
- **NumPy** - Array operations and numerical computing

### Explainable AI (XAI)

- **LIME** (`lime`) - Local Interpretable Model-agnostic Explanations
- **OpenCV** (`cv2`) - Image processing for Grad-CAM heatmaps
- **scikit-image** - Image segmentation for LIME visualizations

### Data Analysis & Visualization

- **Matplotlib** - Plotting training curves and visualizations
- **Seaborn** - Confusion matrix heatmaps
- **scikit-learn** - Metrics (confusion matrix, accuracy)

### Development Tools

- **Jupyter** (`notebook`, `jupyterlab`) - Interactive notebook environment
- **tqdm** - Progress bars during training
- **ipywidgets** - Interactive notebook widgets

## Installation

### Quick Start

```bash
# 1. Create virtual environment
python -m venv .venv

# 2. Activate environment
# Windows:
.venv\Scripts\Activate
# macOS/Linux:
source .venv/bin/activate

# 3. Install all dependencies
pip install -r requirements.txt

# 4. Launch Jupyter
jupyter lab
```

### Notes

- **No IDE required** - Works with any text editor + terminal
- **No manual package hunting** - All dependencies in one file
- **Reproducible** - Same versions across systems

## Tested Environment

- Python 3.10+
- PyTorch 2.5.1 (CPU or GPU)
- CUDA 11.8+ (optional, for NVIDIA GPUs)
- MPS support (Apple Silicon M1/M2/M3/M4)
