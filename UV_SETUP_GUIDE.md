# Data Science Project - Using UV Package Manager

This project uses **`uv`** as the package manager for all Python dependencies. This makes it easy to reproduce the environment and manage dependencies consistently.

## Quick Start

### 1. Install UV (if not already installed)

```bash
pip install uv
```

Or on Windows using PowerShell:

```powershell
pip install uv
```

### 2. Install Project Dependencies

Navigate to the project directory and run:

```bash
uv pip install -e .
```

This will install all dependencies listed in `pyproject.toml`:

- pandas >= 1.3.3
- numpy >= 1.21.2
- matplotlib
- scipy
- seaborn
- ipywidgets
- tqdm
- jupyter
- ipykernel

### 3. Run the Jupyter Notebook

```bash
jupyter notebook
```

Then open `DA0101EN-Review-Introduction.jupyterlite-20221114-1668384000.jupyterlite.ipynb`

## Project Structure

```
Data Science Project/
├── pyproject.toml                           # Project config & dependencies
├── DA0101EN-Review-Introduction...ipynb     # Main tutorial notebook
├── Sample/                                   # Sample data & notebooks
│   ├── Largest_economies.csv
│   └── Simple-API-2--v2-v2.ipynb
└── Stock Price and Revenue/                 # Stock analysis notebooks
    ├── Final Assignment.ipynb
    └── amd.json
```

## Common UV Commands

```bash
# Install all dependencies from pyproject.toml
uv pip install -e .

# Install a specific package
uv pip install pandas

# List installed packages
uv pip list

# Update a package
uv pip install --upgrade pandas

# Create a virtual environment with specific Python version
uv venv --python 3.11

# Use a specific virtual environment
uv run --python .venv/Scripts/python.exe python script.py
```

## Why UV?

- **Fast**: Much faster than pip for dependency resolution
- **Reproducible**: Lock file support ensures consistent environments
- **Simple**: Easy configuration in `pyproject.toml`
- **Python-first**: Built for Python projects specifically

## Managing Dependencies

To add new dependencies, edit `pyproject.toml`:

```toml
[project]
dependencies = [
    "pandas>=1.3.3",
    "numpy>=1.21.2",
    # Add new packages here
    "requests>=2.28.0",
]
```

Then reinstall:

```bash
uv pip install -e .
```

## Troubleshooting

### "uv: command not found"

```bash
pip install uv
```

### "No module named 'piplite'"

This error means the notebook was trying to use browser-based installation. The notebook has been updated to use standard imports instead.

### Virtual Environment Issues

Create a fresh environment:

```bash
uv venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
uv pip install -e .
```

## Next Steps

1. Install dependencies: `uv pip install -e .`
2. Start Jupyter: `jupyter notebook`
3. Run the tutorial cells sequentially
4. Explore the data analysis examples

Happy coding! 🚀
