# Google Play Store App Analytics

An exploratory data analysis and visualization project analyzing thousands of Android apps from the Google Play Store using Pandas and Plotly.

## 📌 Project Overview
The goal of this project is to replicate real-world app market intelligence (similar to Sensor Tower or App Annie) by answering key business and market questions:
- Identifying high-competition vs. high-opportunity app categories.
- Comparing downloads and revenue between Free vs. Paid applications.
- Detecting junk/scam apps and extreme price outliers (e.g., "I am Rich" copycats).
- Estimating top-grossing apps using calculated revenue models.

## 🛠️ Key Techniques & Workflow
- **Data Cleaning & Deduplication:** Removed missing/NaN values and resolved multi-row duplicates using composite column subsets (`subset=['App', 'Type', 'Price']`).
- **Data Type Transformations:** Stripped currency signs (`$`) and comma separators (`,`) from string formats to convert `Installs` and `Price` into numeric types.
- **Outlier Filtering:** Filtered extreme pricing outliers (apps costing > $250) to retain realistic market data.
- **Revenue Estimation:** Computed an estimated gross revenue metric (`Revenue_Estimate = Installs * Price`).
- **Data Visualization:** Built interactive pie and donut charts using `plotly.express` to inspect content ratings and category distributions.

## 🧰 Tech Stack
- **Language:** Python
- **Libraries:** Pandas, Plotly Express
- **Environment:** Google Colab / Jupyter Notebook
