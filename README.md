# Datafun 03 Analytics — Luke Stevers

[![Python 3.14](https://img.shields.io/badge/python-3.14%2B-blue?logo=python)](./pyproject.toml)
[![uv managed](https://img.shields.io/badge/uv-managed-DE5FE9)](https://docs.astral.sh/uv/)
[![Zensical docs](https://img.shields.io/badge/Zensical-docs-purple)](https://zensical.org/)
[![MIT](https://img.shields.io/badge/license-see%20LICENSE-yellow.svg)](./LICENSE)

> A professional Python analytics project demonstrating ETVL data pipelines,
> exploratory data analysis, data visualization, and reproducible workflows.

## GitHub Repository

**My GitHub repository:**

[github.com/lukestevers/Module3](https://github.com/lukestevers/Module3)

## Project Overview

This project demonstrates a professional Python workflow for working with
multiple data sources. The project uses the ETVL pattern:

**Extract → Transform → Verify → Load**

Four different data formats are processed:

- **CSV** — World Happiness data
- **JSON** — astronauts currently in space
- **XLSX** — student feedback
- **TXT** — a plain-text version of *Romeo and Juliet*

The project also includes a custom exploratory data analysis using the
2020 World Happiness dataset.

## Custom Data Analysis

### Research Question

> **Is there a relationship between healthy life expectancy and reported
> happiness among countries in the 2020 World Happiness dataset?**

For this analysis, I selected two numerical variables:

- **Healthy life expectancy**
- **Ladder score**

The Ladder score is the survey's overall measure of reported life evaluation,
while healthy life expectancy provides a measure related to population health.

### Method

I used Python, pandas, and Matplotlib to:

1. Read the `2020_happiness.csv` dataset.
2. Select the `Healthy life expectancy` and `Ladder score` columns.
3. Remove rows with missing values.
4. Create a scatter plot comparing the two variables.
5. Calculate the Pearson correlation coefficient.
6. Interpret the relationship shown by the data.

### Visualization

The project creates a scatter plot:

`data/processed/happiness_life_expectancy_scatter.png`

The horizontal axis represents healthy life expectancy and the vertical axis
represents the Ladder score.

The visualization makes it possible to examine whether the two variables show
an overall positive or negative relationship.

### Observations

The dataset contains **153 country-level observations**.

The Ladder score has:

- **Minimum:** 2.5669
- **Maximum:** 7.8087
- **Mean:** 5.4732
- **Standard deviation:** 1.1123

The scatter plot shows an overall upward pattern. Countries with higher
healthy life expectancy generally appear to have higher Ladder scores.

### Results

The Pearson correlation between healthy life expectancy and Ladder score is:

**r = 0.7703**

This indicates a relatively strong positive linear association between the two
variables in this dataset.

### Interpretation

The results suggest that countries with greater healthy life expectancy tend
to have higher reported happiness scores in the 2020 World Happiness dataset.

However, correlation does **not** demonstrate causation. This analysis cannot
establish that higher healthy life expectancy causes higher happiness.
Other factors may also be related to reported happiness.

The result should therefore be interpreted as an observed association within
this dataset rather than as evidence of a cause-and-effect relationship.

## Skills Demonstrated

This project demonstrates the following skills:

- Python programming
- pandas data analysis
- Matplotlib data visualization
- Reading CSV, JSON, XLSX, and TXT data
- Data extraction and transformation
- Data validation and verification
- Descriptive statistics
- Correlation analysis
- Exploratory Data Analysis (EDA)
- File and path management with `pathlib`
- Logging
- Type hints
- Virtual environment and dependency management with `uv`
- Code formatting and linting
- Git and GitHub version control
- Reproducible project workflows
- GitHub Actions
- Documentation with Zensical

## Project Structure

```text
datafun-03-analytics/
│
├── data/
│   ├── raw/
│   │   ├── 2020_happiness.csv
│   │   ├── astros.json
│   │   ├── Feedback.xlsx
│   │   └── romeo_and_juliet.txt
│   │
│   └── processed/
│       ├── csv_ladder_score_stats.txt
│       ├── happiness_life_expectancy_scatter.png
│       ├── json_astronauts_by_craft.txt
│       ├── xlsx_feedback_github_count.txt
│       └── txt_summary.txt
│
├── docs/
│   └── project documentation
│
├── src/
│   └── datafun/
│       ├── app.py
│       ├── etvl_csv.py
│       ├── etvl_json.py
│       ├── etvl_text.py
│       └── etvl_xlsx.py
│
├── pyproject.toml
├── README.md
└── zensical.toml
