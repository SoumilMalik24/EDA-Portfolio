# FIFA 21 Data Cleaning & Analysis Project

##  Project Overview
This project focuses on **Data Cleaning** and **Exploratory Data Analysis (EDA)** using the "FIFA 21 Messy, Raw Dataset for Cleaning" from Kaggle. 

The primary goal was to transform a raw, unstructured dataset containing mixed data types, special characters, and inconsistent units into a pristine, analytical asset. Post-cleaning, I performed a correlation analysis to identify the key drivers of player market value.

---

##  The Challenge (Dirty Data)
The raw dataset presented several "real-world" data quality issues that needed to be addressed before any analysis could begin:
1.  **Mixed Units:** Heights were stored as both `cm` and `feet/inches` (e.g., "170cm" vs "5'9"). Weights mixed `kg` and `lbs`.
2.  **Currency Strings:** Financial columns (`Value`, `Wage`, `Release Clause`) were stored as strings with currency symbols and suffixes (e.g., "€100M", "€2K").
3.  **Embedded Characters:** Ratings often contained "Star" characters (e.g., "4 ★") preventing numerical calculation.
4.  **Hidden Newlines:** Club names contained inconsistent newline characters (`\nFC Barcelona`).
5.  **Date Logic:** `Joined` dates were strings, and `Contract` duration was unstructured text.

---

##  The Solution (Cleaning Pipeline)
I implemented a robust cleaning pipeline using **Python (Pandas)** and **Regular Expressions (Regex)**:

### 1. Unit Standardization
- Created custom functions to detect input formats (Imperial vs Metric) and convert all Heights to **cm** and Weights to **kg**.

### 2. Financial Parsing
- Stripped "€" symbols.
- Parsed "M" (Millions) and "K" (Thousands) suffixes to convert strings into pure `float64` values.
  - *Example:* `€1.5M` $\rightarrow$ `1500000.0`

### 3. String Manipulation
- Removed "★" from `W/F` (Weak Foot), `SM` (Skill Moves), and `IR` (International Reputation) columns.
- Stripped whitespace and newline characters from the `Club` column.

### 4. Temporal Cleaning
- Converted `Joined` column to `datetime64` objects.
- Parsed the `Contract` column to extract `Contract_Start` and `Contract_End` years as separate integers.

---

##  Key Insights & Findings

After cleaning, I performed an exploratory analysis to understand the football market.

### 1. What drives Market Value?
My correlation analysis revealed that **"Reactions"** (0.49) is the single strongest skill predictor of a player's Market Value—higher than "Dribbling" (0.24) or "Pace". This suggests that mental awareness is valued more highly by the rating algorithm than raw athleticism.

### 2. The Deterministic Market
There is a near-perfect correlation (**0.97**) between `Value` and `Release Clause`. This indicates that release clauses are not arbitrary; they are strictly calculated multipliers of a player's base market value.

### 3. The "Superstar" Economy
Box plot analysis of `Wage` distribution revealed a massive right-skew. The top 1% of players (Superstars) earn exponentially more than the median, confirming a "Power Law" distribution in football economics.

---

##  Visualizations
*(Note: Visuals generated in the notebook)*

### 1. Correlation Matrix: Value Drivers
> *The heatmap highlights the strong relationship between Reactions, Composure, and Market Value.*

### 2. Wage Distribution (Boxplot)
> *Visual confirmation of the outliers (Superstars) in the wage structure.*

---

## 💻 Tech Stack
- **Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Seaborn, Matplotlib, Plotly Express
- **Environment:** Jupyter Notebook / Kaggle

---

## 🚀 How to Run
1. Clone the repository.
2. Install dependencies: `pip install pandas numpy seaborn matplotlib plotly`
3. Open `FIFA_Cleaning_Analysis.ipynb` in Jupyter Notebook.
4. Ensure the raw data file is in the correct path (or download from Kaggle).

---

**Author:** [Your Name]  
**LinkedIn:** [Your LinkedIn Profile Link]