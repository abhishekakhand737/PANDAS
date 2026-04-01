# Pandas Data Analysis — Learning Journal

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-1.x-013243?style=flat-square&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat-square&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active-28a745?style=flat-square)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Advanced-0075ca?style=flat-square)

A structured, self-documented collection of Jupyter Notebooks covering Pandas from first principles to advanced data manipulation techniques. Each notebook reflects what I explored, the problems I solved, and the patterns I internalized along the way.

---

## About This Repository

This repository serves as my personal learning log for mastering data analysis with Pandas. Rather than a course or tutorial set, it is a working reference — built notebook by notebook as I encountered real problems in data handling, cleaning, reshaping, and preparation for machine learning workflows.

---

## Notebook Index

| Notebook | Topic | Key Concepts Covered |
|---|---|---|
| `Pandas_01_(series).ipynb` | Series Fundamentals | Creating Series, indexing, vectorized operations, dtype inference |
| `Pandas_02_(dataframe).ipynb` | DataFrame Basics | Creating DataFrames, column access, shape, dtypes, head/tail |
| `Pandas_03_(read_csv).ipynb` | Reading Datasets | `read_csv()`, file paths, delimiter options, encoding |
| `Pandas_04_(part1_csv).ipynb` | CSV Operations Part 1 | Skipping rows, selecting columns, setting index on load |
| `Pandas_05_(part2_csv).ipynb` | CSV Operations Part 2 | Chunking large files, dtype specification, parsing dates |
| `Pandas_06_(part3_csv).ipynb` | CSV Operations Part 3 | Writing CSVs, handling special characters, export options |
| `Pandas_07_(missing_values).ipynb` | Missing Data Handling | Detecting missing values, `isnull()`, `notnull()`, summary stats |
| `Pandas_08_(null_values).ipynb` | Understanding Null Values | Difference between `NaN`, `None`, and `pd.NA`; propagation behavior |
| `Pandas_09_(Drop_NaN_values).ipynb` | Removing Missing Values | `dropna()`, axis options, threshold-based dropping |
| `Pandas_10_(fillna_function).ipynb` | Filling Missing Values | `fillna()`, forward/backward fill, filling with aggregates |
| `Pandas_11_(replace_function).ipynb` | Data Replacement | `replace()`, regex replacement, dictionary mappings |
| `Pandas_12_(Interpolate_function).ipynb` | Interpolation Methods | Linear, polynomial, and time-based interpolation |
| `Pandas_13_(loc_&_iloc).ipynb` | Data Selection | Label-based (`loc`) vs. position-based (`iloc`) indexing |
| `Pandas_14_(groupby_function).ipynb` | Grouping and Aggregation | `groupby()`, `agg()`, multi-level grouping, split-apply-combine |
| `Pandas_15_(merge_function).ipynb` | Merging Datasets | `merge()`, inner/outer/left/right joins, key conflicts |
| `Pandas_16_(Concat_function).ipynb` | Concatenation | `concat()`, axis control, ignoring vs. preserving index |
| `Pandas_17_(Join_Function).ipynb` | Joining Data | `join()`, index-based joining, suffix handling |
| `Pandas_18_(Pivot_table).ipynb` | Pivot Tables | `pivot_table()`, aggregation functions, multi-index output |
| `Pandas_19_(Melt_Function).ipynb` | Data Reshaping | `melt()`, wide-to-long transformation, id and value variables |
| `Pandas_20_(Delete_index_date).ipynb` | Index and Data Deletion | `drop()`, resetting index, removing rows and columns safely |

---

## What I Learned

### Data Structures

The foundation of Pandas rests on two structures. A **Series** is a one-dimensional labeled array — essentially a dictionary with a consistent dtype. A **DataFrame** is a two-dimensional table where each column is a Series sharing a common index. Understanding how these two objects relate to each other is the single most important conceptual step in learning Pandas.

### Reading and Writing Data

Loading data correctly from the start prevents a large class of downstream issues. Key lessons included always specifying `dtype` for columns where type inference is unreliable (particularly IDs and codes that look numeric), using `parse_dates` to avoid treating timestamps as strings, and chunking large files rather than loading them entirely into memory.

### Missing Data

Missing data handling is where most real-world datasets require the most judgment. I learned to distinguish between dropping rows (`dropna()`), filling with a constant or statistic (`fillna()`), propagating the last known value forward or backward, and using interpolation for time-series or ordered numerical data. The right approach depends on the nature of the missingness — whether it is random, structural, or systematic.

### Data Selection with loc and iloc

`loc` selects by label; `iloc` selects by integer position. Confusing these two is one of the most common sources of bugs in Pandas code. A reliable rule: use `loc` when working with named indexes or column labels, and `iloc` when thinking in terms of row and column numbers.

### GroupBy and Aggregation

The GroupBy mechanism follows a split-apply-combine pattern. Data is split into groups based on a key, a function is applied to each group independently, and the results are combined into a new structure. This is the backbone of most summary and reporting workflows.

### Combining DataFrames

There are three main ways to combine DataFrames, each suited to different situations. `merge()` performs SQL-style joins on column values and is the most flexible. `concat()` stacks DataFrames along an axis and is best for appending rows or columns. `join()` is a convenience wrapper around `merge()` that operates on the index by default.

### Reshaping Data

Pivot tables transform long-format data into wide summaries, grouping by row and column keys and applying an aggregation function. Melt does the reverse — converting wide tables into long format where each row represents a single observation. Knowing when to use each is essential for preparing data for visualization libraries and machine learning pipelines.

---

## Visualizations Covered

Several notebooks include plots generated with Matplotlib and Pandas' built-in `.plot()` interface. Below is a summary of the chart types used and what each communicates:

| Plot Type | Used In | What It Shows |
|---|---|---|
| Bar chart | GroupBy, Pivot Table notebooks | Comparison of aggregated values across categories |
| Line chart | Interpolation, CSV notebooks | Trends over ordered sequences; makes gaps from missing data visible |
| Heatmap (via pivot) | Pivot Table notebook | Relationship between two categorical variables through color intensity |
| Box plot | Missing value notebooks | Distribution of a numerical variable including median, quartiles, and outliers |
| Histogram | DataFrame basics | Frequency distribution of a continuous variable |

A bar chart is appropriate when comparing discrete categories. A line chart is appropriate when the x-axis represents order or time. A heatmap built from a pivot table reveals interaction patterns between two categorical dimensions. Box plots are particularly useful for detecting outliers before cleaning.

---

## Setup and Installation

**Clone the repository**

```bash
git clone https://github.com/abhishekakhand737/PANDAS.git
cd PANDAS
```

**Install dependencies**

```bash
pip install pandas numpy notebook matplotlib
```

**Launch Jupyter**

```bash
jupyter notebook
```

---

## Tech Stack

| Tool | Version | Purpose |
|---|---|---|
| Python | 3.x | Runtime environment |
| Pandas | 2.x | Data manipulation and analysis |
| NumPy | 1.x | Numerical operations underlying Pandas |
| Jupyter Notebook | Latest | Interactive development and documentation |
| Matplotlib | Latest | Plotting and visualization |

---

## Author

**Abhishek Akhand**
B.Tech — Artificial Intelligence and Data Science.

GitHub: [abhishekakhand737](https://github.com/abhishekakhand737)

---

*Data analysis is not about the tools — it is about asking the right questions and knowing how to find the answers in the data.*
