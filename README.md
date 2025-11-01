# ACIT4610 Exam - XAI Image Classification

All notebooks are designed to run **independently of any IDE** — you only need Python and Jupyter installed.

---

## Quick Setup & Onboarding Guide

This section helps you get up and running quickly — from environment setup to running notebooks — whether you use an IDE or just the terminal.

---

### 1. Create and activate a virtual environment

You can create the virtual environment using either your **IDE’s built-in tools** (PyCharm, VS Code, etc.) or directly in the **terminal**, which works everywhere.

#### Windows (PowerShell)
```powershell
python -m venv .venv
.venv\Scripts\Activate
```

#### macOS / Linux (bash or zsh)
```bash
python3 -m venv .venv
source .venv/bin/activate
```

After activation, your terminal prompt should start with `(.venv)`.

---

### 2. Install dependencies

Make sure you’re in the project folder (where `requirements.txt` is located), then run:

```bash
pip install -r requirements.txt
```

This installs all core libraries, including:
- `numpy`, `pandas`, `matplotlib`
- `notebook`, `jupyterlab`
- `scipy`, `seaborn`
- and other helper tools

> **Tip:** Add or update dependencies in `requirements.txt` **manually**.  
> Avoid using IDE prompts like *"Sync Project with requirements.txt"* — they can clutter the file with unnecessary or duplicate packages.  
> Some libraries (like `setuptools`, `pip`, or `wheel`) are automatically installed when you install Python, so there’s no need to include them in the list.

---

### 3. Run Jupyter notebooks (IDE-independent)

Once your virtual environment is active, launch Jupyter Lab or Notebook:

```bash
jupyter lab
```
or
```bash
jupyter notebook
```

Then open any notebook to begin working with the project.

---

## Project Files Overview

- **`.gitattributes`** – Configures Git behavior (e.g., line endings, file handling).  
- **`.gitignore`** – Tells Git which files/folders to ignore (e.g., `.venv/`, cache files).  
- **`README.md`** – Contains setup, usage, and environment instructions.  
- **`requirements.txt`** – Lists Python dependencies. It allows you to install all required packages **in one command**, instead of one by one — saving time and reducing setup frustration.

---

## Notes

- **No IDE required:** You can run everything from the terminal and browser.  
- **Virtual environment benefits:** Keeps dependencies isolated per project.  
- **Reproducibility:** Use the same `requirements.txt` across systems for consistent results.
