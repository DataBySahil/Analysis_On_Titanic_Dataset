# Titanic Dataset: Exploratory Data Analysis

An exploratory data analysis of the classic Titanic passenger dataset using Python, Pandas, Matplotlib, and Seaborn. The notebook examines the structure and quality of the data, summarizes its numerical and categorical variables, and visualizes patterns associated with passenger survival.

## Project Overview

The analysis in [`001.ipynb`](001.ipynb) follows a compact, reproducible workflow:

1. Load the Titanic dataset directly from the public Seaborn data repository.
2. Inspect the first records, dimensions, data types, and missing values.
3. Calculate descriptive statistics including mean, median, mode, standard deviation, variance, minimum, and maximum values.
4. Explore age, fare, sex, passenger class, and survival distributions.
5. Use box plots and a scatter plot to inspect spread, outliers, and the relationship between age and fare.
6. Compare survival counts by sex and passenger class.
7. Calculate and visualize correlations between numeric variables with a heatmap and pair plot.

## Key Findings

The notebook's exploratory results indicate that:

- The dataset contains **891 passengers** and **15 columns**.
- `age` has 714 non-null values, while `deck` is substantially incomplete with 203 non-null values. `embarked` and `embark_town` each have two missing values.
- Survival is positively correlated with `fare` (approximately **0.26**) and negatively correlated with `pclass` (approximately **-0.34**). Since lower `pclass` values represent higher passenger classes, this is consistent with better survival outcomes among higher-class passengers.
- `pclass` and `fare` have a moderate negative correlation (approximately **-0.55**), reflecting the relationship between class and ticket price.
- `sibsp` and `parch` show a positive relationship (approximately **0.41**), suggesting that family travel variables are not independent.
- Age and fare have very little linear correlation (approximately **0.096**).

These are descriptive relationships, not evidence that fare or class alone caused survival. The notebook does not train or evaluate a predictive model.

## Dataset

The data is loaded at runtime from:

<https://raw.githubusercontent.com/mwaskom/seaborn-data/master/titanic.csv>

Important fields include:

| Field | Description |
| --- | --- |
| `survived` | Survival indicator: `0` = no, `1` = yes |
| `pclass` | Passenger class: `1`, `2`, or `3` |
| `sex` | Passenger sex |
| `age` | Passenger age in years |
| `sibsp` | Number of siblings or spouses aboard |
| `parch` | Number of parents or children aboard |
| `fare` | Passenger fare |
| `embarked` | Port of embarkation |
| `class` | Text label for passenger class |
| `alive` | Text survival label |
| `alone` | Whether the passenger traveled alone |

## Getting Started

### Requirements

- Python 3.9 or newer
- Jupyter Notebook, JupyterLab, or VS Code with the Jupyter extension
- Internet access when the notebook is first loading the dataset

### Installation

Create and activate a virtual environment, then install the notebook dependencies:

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

```bash
python -m pip install --upgrade pip
python -m pip install pandas numpy matplotlib seaborn jupyter
```

### Run the Analysis

Launch Jupyter:

```bash
jupyter notebook
```

Open [`001.ipynb`](001.ipynb) and run the cells from top to bottom. The notebook is stateful, so executing the import and data-loading cells first ensures every later analysis cell has the required `df` and `correlation` variables.

In VS Code, open the notebook, select the Python environment containing the dependencies, and use **Run All**.

## Visualizations

The notebook generates:

- Age and fare histograms with KDE curves
- Sex, passenger class, and survival count plots
- Fare and age box plots
- Age-versus-fare scatter plot
- Survival comparisons by sex and passenger class
- A numeric correlation heatmap
- A pair plot for survival, age, fare, and passenger class

## Project Structure

```text
.
├── 001.ipynb   # Exploratory analysis notebook
└── README.md   # Project documentation
```

## Notes and Limitations

- The dataset is downloaded from a remote URL rather than stored locally, so the analysis requires network access.
- Missing values are inspected but are not imputed or otherwise cleaned in the current notebook.
- Correlation measures linear association and should not be interpreted as causation.
- The analysis is intended for learning and exploration; it is not a complete statistical study of Titanic survival.

## Possible Extensions

- Add missing-value handling and document the chosen strategy.
- Compare survival rates instead of only survival counts.
- Add grouped summaries and confidence intervals.
- Engineer family-size and title features.
- Build and evaluate a baseline classification model with a held-out test set.
