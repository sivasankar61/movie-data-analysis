# 🎬 Netflix Movie Dataset — Exploratory Data Analysis (EDA)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-11557c)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A comprehensive Exploratory Data Analysis (EDA) project on a Netflix movie dataset (`mymoviedb.csv`), covering data cleaning, preprocessing, feature engineering, and insightful visualizations using Python.

---

## 📁 Project Structure

```
netflix-eda/
│
├── netflix_eda.ipynb        # Main Jupyter Notebook with full analysis
├── mymoviedb.csv            # Dataset (Netflix movie records)
└── README.md                # Project documentation
```

---

## 📊 Dataset Overview

The dataset contains **9,827 rows** and **9 columns** with details about movies available on Netflix.

| Column | Description |
|---|---|
| `Title` | Movie title |
| `Release_Date` | Release date of the movie |
| `Genre` | Comma-separated genre tags |
| `Vote_Average` | Average user vote score |
| `Vote_Count` | Total number of votes |
| `Popularity` | Popularity score |
| `Overview` | Short movie description |
| `Original_Language` | Language of the movie |
| `Poster_Url` | URL to the movie poster |

---

## 🛠️ Data Cleaning & Preprocessing

The following preprocessing steps were applied to make the data analysis-ready:

- **Type Conversion** — `Release_Date` cast to `datetime` and reduced to year only; `Vote_Count` cast to `int`; `Vote_Average` cast to `float`
- **Column Dropping** — Removed `Overview`, `Original_Language`, and `Poster_Url` as they were not useful for analysis
- **Duplicate Check** — Verified no duplicate records existed
- **Missing Values** — Dropped rows with remaining NaN values after categorization
- **Genre Exploding** — Multi-genre comma-separated strings were split and exploded into individual rows (one genre per row per movie) to enable accurate genre-level analysis
- **Vote Average Categorization** — A custom function `catigorize_col()` was used to bin `Vote_Average` into four categories using quartile-based edges:

| Category | Description |
|---|---|
| `not_popular` | Bottom 25% of vote average |
| `below_avg` | 25th–50th percentile |
| `average` | 50th–75th percentile |
| `popular` | Top 25% of vote average |

---

## 🔍 Key Questions Explored

| # | Question | Answer |
|---|---|---|
| 1 | What is the most frequent genre released on Netflix? | **Drama**, followed by Comedy and Action |
| 2 | Which vote average category has the most movies? | **Average**, with a near-even distribution across all categories |
| 3 | Which movie has the highest popularity? | **Spider-Man: No Way Home** |
| 4 | Which movie has the lowest popularity? | **The United States vs. Billie Holiday** |
| 5 | Which year had the most movie releases? | Post-**2000s** dominate; significant growth in modern-era production |

---

## 📈 Visualizations

**1. Genre Distribution**
A horizontal count plot showing the frequency of each genre across the dataset. Drama is the dominant genre, while Western, Documentary, and TV Movie appear least frequently.

**2. Vote Average Distribution**
A count plot of the four vote average categories reveals an almost balanced spread, with the `average` category having a slight edge.

**3. Release Year Histogram**
A histogram of release years shows a right-skewed distribution — very few movies before 1980, with a sharp rise after 2000, reflecting the global expansion of film production.

---

## 🧰 Libraries Used

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

| Library | Purpose |
|---|---|
| `NumPy` | Numerical operations |
| `Pandas` | Data loading, cleaning, transformation |
| `Matplotlib` | Base plotting |
| `Seaborn` | Statistical visualizations |

---

## ▶️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/netflix-eda.git
   cd netflix-eda
   ```

2. Install dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn
   ```

3. Launch the notebook:
   ```bash
   jupyter notebook netflix_eda.ipynb
   ```

> Make sure `mymoviedb.csv` is in the same directory as the notebook before running.

---

## 💡 Insights Summary

- **Drama, Comedy, and Action** are the three most produced genres on Netflix.
- **Modern movies dominate** the platform — the majority were released after 2000.
- **Vote averages are evenly distributed**, suggesting Netflix hosts a diverse mix of critically acclaimed and average-rated content.
- **Spider-Man: No Way Home** holds the highest popularity score in the dataset.
- The project demonstrates a full EDA pipeline: ingestion → cleaning → transformation → visualization → insights.

---

## 🙋 Author

**Shiva Sankar**
Feel free to connect at sontyanasivasankar@gmail.com or raise issues for discussion!

---

