# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository is a learning environment for applying fastai-based machine learning to ambulatory healthcare scenarios. The focus is deep understanding of the full ML lifecycle, not leaderboard performance. Each notebook explores practical healthcare problems such as risk prediction, operational efficiency, and decision support, with careful attention to data leakage, bias, and clinical context.

## Python Environment

This project uses **Python 3.12** exclusively with a virtual environment named `myenv`.

The user has multiple Python versions installed, so always use the explicit interpreter:

```bash
python3.12 -m venv myenv
source myenv/bin/activate
```

**Critical**: Always activate the virtual environment before running Python code or installing packages. The venv is located at `myenv/` and is gitignored.

## Common Commands

### Environment Setup

Create and activate the virtual environment:
```bash
python3.12 -m venv myenv
source myenv/bin/activate
```

Install dependencies:
```bash
pip install -r requirements.txt
```

Verify fastai installation:
```bash
python -c "import fastai; print(fastai.__version__); print(fastai.__file__)"
```

### Jupyter Setup

Register the virtual environment as a Jupyter kernel:
```bash
python -m ipykernel install --user --name fastai-medical-ml --display-name "fastai-medical-ml (py312)"
```

Verify kernel registration:
```bash
jupyter kernelspec list
```

Launch Jupyter Notebook:
```bash
jupyter notebook
```

### Working with Notebooks

Notebooks are located in `notebooks/` and should use the `fastai-medical-ml (py312)` kernel.

Naming convention: `00_descriptive_name.ipynb` (numbered prefixes for ordering).

When creating notebooks, verify the correct kernel and environment by running:
```python
import fastai
import sys
print(fastai.__version__)
print(sys.executable)  # Should point to myenv/bin/python
```

## Project Structure

- `notebooks/`: Jupyter notebooks for hands-on ML experiments
- `src/`: Python source code (currently empty, for future utilities/modules)
- `data/`: Local datasets (gitignored)
- `logs/`: Training logs and experiment outputs (gitignored)
- `myenv/`: Virtual environment (gitignored)

## Key Dependencies

- **fastai**: Core ML framework (automatically installs PyTorch)
- **jupyter** & **ipykernel**: Notebook environment
- **pandas**: Data manipulation
- **scikit-learn**: Traditional ML utilities
- **ddgs**: DuckDuckGo Search (for data collection from notebooks)

## Development Philosophy

### Focus on Understanding, Not Performance
- Emphasize learning the full modeling lifecycle: problem framing, EDA, feature engineering, training, evaluation, error analysis
- Document clinical and operational caveats
- Explicitly note limitations of public/synthetic datasets

### Healthcare-Specific Considerations
- Be mindful of data leakage in temporal healthcare data
- Consider bias and fairness in clinical contexts
- Document assumptions and limitations clearly
- Focus on practical scenarios: chronic disease management, patient access, revenue cycle operations

### Code Quality
- Keep notebooks focused and well-documented
- Use descriptive variable names
- Comment sparingly (code should be self-explanatory)
- Use tqdm for large loops to track progress
- Use red-green refactor approach when building new functionality

## Working with Data

Image files are gitignored (`.jpg`, `.jpeg`, `.png`, `.gif`, `.bmp`, `.tiff`), as are specific model export directories like `bird_or_not/`.

Store datasets in `data/` directory - this is gitignored to prevent committing large files.

## Notes for AI Assistants

- Always activate `myenv` before running Python commands
- When creating new notebooks, always verify the kernel is `fastai-medical-ml (py312)`
- This is a learning repository - prioritize clarity and educational value over optimization
- The user is female (use she/her pronouns)
- The user refers to you as "Auntie CC"
