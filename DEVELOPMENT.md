# Development Guide

This guide provides detailed instructions for setting up a development environment and working with the Domain Name Prediction System.

## Quick Start

```bash
# Clone repository
git clone https://github.com/bosszukung/Domain-Name-Prediction.git
cd Domain-Name-Prediction

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

## Full Development Environment Setup

### Step 1: Prerequisites

Verify you have:
- Python 3.8 or higher
- pip (Python package manager)
- git (version control)

```bash
python --version  # Should be 3.8+
pip --version
git --version
```

### Step 2: Clone Repository

```bash
git clone https://github.com/bosszukung/Domain-Name-Prediction.git
cd Domain-Name-Prediction
```

### Step 3: Create Virtual Environment

```bash
# Create venv
python -m venv venv

# Activate venv
# On macOS/Linux:
source venv/bin/activate

# On Windows:
venv\Scripts\activate
```

### Step 4: Install Dependencies

```bash
# Upgrade pip
pip install --upgrade pip

# Install requirements
pip install -r requirements.txt

# Optional: Install development tools
pip install black flake8 pytest mypy
```

### Step 5: Verify Installation

```bash
# Check Python packages
pip list

# Test Jupyter
jupyter --version

# Test sklearn
python -c "import sklearn; print(sklearn.__version__)"
```

## Working with Jupyter Notebooks

### Launching Jupyter

```bash
jupyter notebook
# or
jupyter lab
```

### Common Tasks

**Clear Output:**
```
Cell → All Output → Clear
```

**Restart Kernel:**
```
Kernel → Restart & Clear Output
```

**Restart and Run All:**
```
Kernel → Restart & Run All
```

## Running the Pipeline

### Option 1: Run Entire Notebook
- Open `Code/Domain Name Prediction System.ipynb`
- Click `Kernel → Restart & Run All`

### Option 2: Run Cell by Cell
- Open notebook
- Select cell
- Press Shift + Enter to execute
- Review output before proceeding

## Testing

### Run Tests
```bash
pytest
```

### Check Code Quality
```bash
# Format code
black .

# Check style
flake8 .

# Type checking
mypy .
```

## Troubleshooting

### Virtual Environment Issues

**Problem:** `activate` command not found
```bash
# Solution: Create venv again
python -m venv venv
source venv/bin/activate  # macOS/Linux
# or
venv\Scripts\activate  # Windows
```

**Problem:** Permission denied
```bash
# Solution: On macOS/Linux
chmod +x venv/bin/activate
```

### Dependency Issues

**Problem:** Import error for pandas/sklearn
```bash
# Solution: Reinstall requirements
pip install --upgrade -r requirements.txt
```

**Problem:** Version conflicts
```bash
# Solution: Clear and reinstall
pip install --force-reinstall -r requirements.txt
```

### Jupyter Issues

**Problem:** Kernel not found
```bash
# Solution: Install ipykernel
pip install ipykernel
python -m ipykernel install --user
```

**Problem:** Kernel crashes on import
```bash
# Solution: Restart kernel
Kernel → Restart
```

**Problem:** Data not loading
```bash
# Solution: Verify file path
import os
os.getcwd()  # Check working directory
os.listdir()  # Check files in directory
```

### Data Issues

**Problem:** CSV file not found
```python
# Solution: Check path
import os
print(os.path.abspath('DataSet/coursework_data.csv'))
```

**Problem:** Encoding errors when loading CSV
```python
# Try different encoding
pd.read_csv('DataSet/coursework_data.csv', encoding='utf-8')
pd.read_csv('DataSet/coursework_data.csv', encoding='latin-1')
```

### Performance Issues

**Problem:** Notebook runs slowly
- Reduce dataset size for testing
- Use subset of features
- Check available RAM: `top` (macOS/Linux) or Task Manager (Windows)

**Problem:** Memory error with large datasets
```python
# Read data in chunks
chunks = pd.read_csv('DataSet/coursework_data.csv', chunksize=1000)
data = pd.concat([chunk for chunk in chunks])
```

## Code Style

### Format Code with Black

```bash
black Code/
```

### Check Code Quality

```bash
flake8 Code/ --max-line-length=100
```

### Type Hints

```python
def calculate_metrics(y_true: list, y_pred: list) -> dict:
    """Calculate evaluation metrics."""
    pass
```

## Git Workflow

### Creating Feature Branch
```bash
git checkout -b feature/your-feature-name
```

### Committing Changes
```bash
git add .
git commit -m "description of changes"
```

### Pushing Changes
```bash
git push origin feature/your-feature-name
```

### Creating Pull Request
Visit: https://github.com/bosszukung/Domain-Name-Prediction/pulls

## Documentation

### Update README
- Edit `README.md` with project changes
- Test markdown rendering on GitHub

### Add Docstrings
```python
def extract_features(domain):
    """
    Extract features from domain name.
    
    Parameters
    ----------
    domain : str
        Domain name to analyze
        
    Returns
    -------
    dict
        Dictionary of extracted features
        
    Example
    -------
    >>> extract_features("example.com")
    {'length': 11, 'hyphens': 0}
    """
```

### Update Requirements
```bash
# Freeze current environment
pip freeze > requirements.txt

# Or manually update with versions
```

## Debugging

### Add Print Statements
```python
# Check data shape
print(f"Shape: {data.shape}")
print(f"Columns: {data.columns.tolist()}")
```

### Use Debugger
```python
import pdb
pdb.set_trace()  # Execution pauses here
# Use commands: n (next), s (step), c (continue), p (print)
```

### Check Variable Types
```python
print(type(variable))
print(isinstance(variable, pd.DataFrame))
```

## Performance Profiling

```python
import time

start = time.time()
# Code to profile
end = time.time()
print(f"Execution time: {end - start:.2f} seconds")
```

## Project Structure Notes

```
Domain-Name-Prediction/
├── Code/
│   └── Domain Name Prediction System.ipynb  # Main analysis
├── DataSet/
│   └── coursework_data.csv                  # Training data
├── Report/                                   # Analysis results
├── README.md                                 # Main documentation
├── CONTRIBUTING.md                          # Contribution guide
├── DEVELOPMENT.md                           # This file
├── SECURITY.md                              # Security policy
├── LICENSE                                  # MIT License
├── .gitignore                               # Git ignore rules
└── requirements.txt                         # Dependencies
```

## Additional Resources

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [Pandas Documentation](https://pandas.pydata.org/)
- [Jupyter Documentation](https://jupyter.org/)
- [Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/)

## Getting Help

1. Check existing GitHub Issues
2. Search documentation
3. Review notebooks for examples
4. Open a new Issue with details
5. Contact maintainer if needed

## Next Steps

- Explore the Jupyter notebook
- Run the complete pipeline
- Experiment with different models
- Contribute improvements

Happy coding! 🚀
