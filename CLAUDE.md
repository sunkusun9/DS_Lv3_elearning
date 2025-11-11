# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Korean-language e-learning course repository for **Level 3 Data Science Advanced Training** (전자 DX Level 3). The repository contains Jupyter notebooks covering advanced data analysis topics for data science certification preparation.

**Important**: Content may differ from the actual video lectures as corrections and additions are made after e-learning production.

## Repository Structure

- **Root**: Main Jupyter notebooks (numbered 1-1 through 4-4) - these are the primary working notebooks organized by topic and chapter
- **`data/`**: Dataset files (CSV, PKL, JPG, TSV) used across notebooks
- **`prev_version/`**: Previous version notebooks (both .ipynb and .Rmd formats)
- **`rmd/`**: R Markdown source files (.Rmd) and rendered HTML files (.nb.html)
- **`ppt_to_markdown.ipynb`**: Utility notebook for converting PowerPoint presentations to markdown-formatted Jupyter notebooks

## Course Structure

The notebooks follow a structured curriculum:

1. **Data Understanding** (1-x)
   - 1-1: Data classification and types
   - 1-2: Missing values and outlier handling
   - 1-3: Data transformation
   - 1-4: Data visualization (content may be in development)

2. **Probability and Statistics** (2-x)
   - 2-1: Probability introduction (통계와 확률)
   - 2-2: Probability distributions (확률 분포)
   - 2-3: Hypothesis testing (가설 검정)
   - 2-4: Point and interval estimation (점 추정과 구간 추정)
   - 2-5: Advanced estimation methods (고급 추정법)
   - 2-6: Linear regression analysis (선형회귀 분석)
   - 2-7: Association analysis (연관성 분석)

3. **Machine Learning** (3-x)
   - 3-1: Machine learning fundamentals (머신 러닝)
   - 3-2: Parametric models (모수적 모델)
   - 3-3: Non-parametric models (비모수적 모델)
   - 3-4: Support Vector Machines (SVM)
   - 3-5: Ensemble models (앙상블 모델)
   - 3-6: Clustering (군집화)
   - 3-7: Dimensionality reduction (차원 축소)
   - 3-8: Generalization techniques (일반화 기법)

4. **Deep Learning** (4-x)
   - 4-1: Perceptron (퍼셉트론)
   - 4-2: Neural network architecture (신경망의 구성)
   - 4-4: Deep neural networks (심층신경망)

## Development Environment

### Python Environment

This repository uses **legacy Python package versions** for compatibility:
- Python: Likely 3.7 or 3.8 (based on package versions)
- NumPy: 1.18.5 (older version)
- Pandas: 0.25.1 (older version)
- scikit-learn: 0.21.3
- matplotlib: 3.5.3
- seaborn: 0.12.2
- XGBoost: 0.80

### Installing Dependencies

```bash
pip install -r requirements.txt
```

**Warning**: The requirements.txt uses very old package versions. Modern Python versions (3.10+) may have compatibility issues. Python 3.7-3.8 is recommended.

### Running Notebooks

Launch Jupyter:
```bash
jupyter notebook
```

Or use JupyterLab:
```bash
jupyter lab
```

## Working with Notebooks

### Notebook Naming Convention

Notebooks use Korean names with a pattern: `{section}-{subsection} {topic name}.ipynb`
- Example: `1-1 데이터의 이해.ipynb` (1-1 Understanding Data)
- Example: `3-4 SVM.ipynb` (3-4 SVM)

### Content Structure

Most notebooks follow this structure:
1. **Markdown header**: Chapter/section title
2. **Theory sections**: Markdown cells with tables, mathematical formulas, and explanations
3. **Code examples**: Python code cells demonstrating concepts
4. **Visualizations**: Plots using matplotlib/seaborn
5. **Practical exercises**: Code cells for hands-on practice

### Data File References

Notebooks reference data files using relative paths from the root:
- `data/titanic.csv`
- `data/credit.pkl`
- `data/space_titanic.csv`
- etc.

When editing notebooks, ensure data file paths remain correct.

## Git Branch Strategy

- **`main`**: Main branch (stable version)
- **`1-2nd-edition`**: Current working branch (second edition updates)

When creating pull requests, use `main` as the base branch.

## Special Utilities

### PPT to Markdown Converter (`ppt_to_markdown.ipynb`)

A utility for converting PowerPoint presentations to Jupyter notebooks with markdown cells. This is version 3 (v3) with improved text joining capabilities.

**Features**:
- Extracts text from PPTX paragraphs with proper sentence reconstruction
- Preserves bullet points, line breaks
- Converts embedded images to base64 data URIs
- Extracts tables and converts to markdown tables
- Extracts mathematical equations

**Usage pattern** (from the notebook):
```python
pptx_path = "path/to/presentation.pptx"
out_ipynb = "output_notebook.ipynb"
build_output_notebook(pptx_path, out_ipynb)
```

## Code Style Notes

- Korean comments and docstrings are standard in this codebase
- Variable names may mix English and Korean
- Mathematical formulas are often rendered in LaTeX within markdown cells
- Code examples prioritize educational clarity over production optimization

## Common Tasks

### Editing a topic notebook
1. Open the relevant numbered notebook (e.g., `1-2 데이터의 정제.ipynb`)
2. Make changes to markdown or code cells
3. Test code cells sequentially to ensure they still work
4. Verify data file paths are correct

### Adding new content
1. Follow the existing numbering scheme
2. Use markdown headers for structure
3. Include both theory (markdown) and code examples
4. Test with datasets in `data/` directory

### Updating from previous version
- Previous versions are preserved in `prev_version/` and `rmd/`
- R Markdown equivalents may exist for some topics
- When porting content, ensure Python code compatibility with the package versions

## Platform Notes

- Repository is on Windows (`win32` platform)
- File paths use backslashes (`\`) on Windows
- Line endings may be CRLF
- When working cross-platform, be mindful of path separators
