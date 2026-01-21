# Using Epydemix in Python

This guide assumes you have Anaconda installed. If not, see [python-setup.md](python-setup.md) first.

## Installation

### Step 1: Open a Terminal

**macOS**
- Open Spotlight (Cmd + Space), type "Terminal", and press Enter

**Windows**
- Open the Start menu, search for "Anaconda Prompt", and open it
- Note: Use Anaconda Prompt, not the regular Command Prompt

**Linux**
- Open your terminal application (Ctrl + Alt + T on most distributions)

### Step 2: (Optional) Create a Dedicated Environment

We recommend creating a separate environment for the workshop:

```bash
conda create -n epydemix-workshop python=3.11
conda activate epydemix-workshop
```

### Step 3: Install Epydemix

**Option A: conda-forge (Recommended for Anaconda users)**

```bash
conda install -c conda-forge epydemix
```

**Option B: pip**

```bash
pip install epydemix
```

Both methods work, but conda-forge handles dependencies better within Anaconda environments.

## Verify Installation

### Opening a Jupyter Notebook

From your terminal (with your environment activated):

```bash
jupyter notebook
```

This opens Jupyter in your browser. Click **New → Python 3** to create a notebook.

Alternatively, use **Anaconda Navigator**: launch it from your applications, then click "Launch" under Jupyter Notebook.

### Test the Installation

In a notebook cell, run:

```python
from epydemix import EpiModel

# Define a basic SIR model
model = EpiModel(
    name="SIR Model",
    compartments=["S", "I", "R"],
)

# Add transitions: infection and recovery
model.add_transition(source="S", target="I", params=(0.3, "I"), kind="mediated")
model.add_transition(source="I", target="R", params=0.1, kind="spontaneous")

# Run simulations
results = model.run_simulations(
    start_date="2024-01-01",
    end_date="2024-04-10",
    Nsim=10,
)
```

If no errors appear, you're ready to go.

## Troubleshooting

**"conda: command not found"**
- Make sure you're using Anaconda Prompt (Windows) or that conda is in your PATH

**"Module not found" after installation**
- Ensure you're in the correct environment: `conda activate epydemix-workshop`
- Try reinstalling: `conda install -c conda-forge epydemix --force-reinstall`
