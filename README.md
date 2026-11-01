# Google Play Store App Analytics

An exploratory data analysis and visualization project analyzing thousands of Android apps from the Google Play Store using Pandas and Plotly.

## Project Overview
The goal of this project is to replicate real-world app market intelligence (similar to Sensor Tower or App Annie) by answering key business and market questions:
- Identifying high-competition vs. high-opportunity app categories.
- Comparing downloads and revenue between Free vs. Paid applications.
- Detecting junk/scam apps and extreme price outliers (e.g., "I am Rich" copycats).
- Estimating top-grossing apps using calculated revenue models.
- Analyzing category concentration and market spread to evaluate developer risk.

---

## Key Techniques & Workflow
- **Data Cleaning & Deduplication:** Handled missing/NaN values and resolved multi-row duplicates using composite column subsets (`subset=['App', 'Type', 'Price']`).
- **Data Type Transformations:** Stripped currency signs (`$`) and comma separators (`,`) to convert `Installs` and `Price` into numeric types.
- **Outlier Filtering:** Filtered extreme pricing outliers (apps costing > $250) to remove dummy/scam apps and preserve realistic market distribution.
- **Revenue Estimation:** Computed an estimated gross revenue metric (`Revenue_Estimate = Installs * Price`).
- **Nested Column Extraction:** Decomposed multi-genre string entries separated by semicolons using `.str.split(';', expand=True)` and reshaped them via `.stack()` to accurately count unique individual genres.
- **Interactive Visualizations:** Leveraged `plotly.express` to generate Pie, Donut, Vertical/Horizontal Bar Charts, Grouped Bar Charts, Log-scaled Scatter Plots, and Box Plots.

---

## Key Findings & Market Insights
- **Market Dominance:** Over 80% of apps are rated "Everyone", and the vast majority are Free. Free apps have a median download count of ~500,000, whereas Paid apps only achieve a median of ~5,000 downloads (a ~100x drop).
- **Category Popularity vs. Competition:** While `Family` and `Game` have the highest number of apps (highest competition), `Game` and `Tools` generate the largest total download volumes.
- **Market Concentration:** In categories like `Video Players` and `Entertainment`, downloads are heavily concentrated among a few dominant giants. Conversely, `Family` and `Tools` have downloads distributed widely across numerous titles.
- **Revenue & Pricing Strategy:** The overall median price for paid Android apps is **$2.99**. The top-grossing paid app title is **Minecraft** (approx. $70M revenue), with 7 out of the top 10 highest-grossing paid apps belonging to the gaming genre.

---

## Visualizations

| Chart | Description |
| :--- | :--- |
| ![Category Concentration](images/category_concentration_scatter_plot.png) | **Market Concentration:** Log-scaled scatter plot comparing number of apps vs total downloads across categories. |
| ![Free vs Paid Downloads](images/free_vs_paid_downloads_boxplot.png) | **Download Disparity:** Box plot showing downloads given up when choosing a paid model. |
| ![Paid App Revenue](images/paid_apps_revenue_estimate_boxplot.png) | **Ballpark Revenue:** Estimated gross earnings across different categories for paid apps. |
| ![Price per Category](images/price_per_category_boxplot.png) | **Pricing Benchmarks:** Median and quartile prices across categories for paid applications. |
| ![Top Genres](images/top_genres_distribution_bar.png) | **Top Genres:** Frequency distribution of un-nested genres using the `Agsunset` continuous scale. |
| ![Content Rating](images/content_rating_donut_chart.png) | **Target Demographics:** Donut chart illustrating content rating proportions across the store. |

---

## Tech Stack
- **Language:** Python
- **Libraries:** Pandas, Plotly Express
- **Environment:** Google Colab / Jupyter Notebook
