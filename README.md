# Food Commodity Price Analysis (2018–2024)

Exploratory data analysis of daily prices for 10 staple food commodities in Indonesia over 7 years. The project examines long-term trends, seasonality, year-over-year growth, and correlations between commodities, with visualizations built in Python.

## Highlights

- Analyzed **2,557 daily price records** across **10 commodities** (2018–2024), with no missing values or duplicate rows.
- Quantified average **year-over-year price growth**: garlic (**+11.7%**) and shallots (**+10.9%**) rose fastest, while rice rose the slowest (**+3.75%**).
- Identified monthly seasonal movements and visualized relationships between commodity prices with correlation heatmaps and pairwise scatter plots.

## Dataset

| Item | Detail |
|---|---|
| Location | Jakarta |
| Period | 2018–2024, daily |
| Size | 2,557 rows, 12 columns |
| Unit | Price in IDR |

**Commodities (10):** Rice (Beras), Chicken Meat (Daging Ayam), Chicken Eggs (Telur Ayam), Shallots (Bawang Merah), Garlic (Bawang Putih), Red Chili (Cabai Merah), Green Cayenne Pepper (Cabai Rawit Hijau), Red Cayenne Pepper (Cabai Rawit Merah), Cooking Oil (Minyak Goreng), Sugar (Gula Pasir)

**Data quality checks:** column types, missing-value percentage, and duplicate records (0 duplicates, 0 missing values).

> The dataset is not included in this repository. Place your Excel file in the project folder and update the file path in the notebook.

## Methodology

1. **Data inspection:** `head`/`tail`, `info`, shape, column names, duplicate and missing-value checks.
2. **Feature engineering:** extracted `Year`, `Month`, and weekday name from the date column.
3. **Trend and seasonality analysis:**
   - Full-period price trend per commodity (10-panel time-series plot)
   - Annual and monthly average prices per commodity
   - Month-by-year comparison of average prices (e.g., rice, 2018–2024)
   - Boxplots by year and by month (e.g., chicken meat) to inspect spread and outliers
4. **Correlation analysis:** correlation matrix across all commodities, shown as a heatmap and as a pairwise scatter grid annotated with Pearson's *r*.
5. **Growth quantification:** average nominal and percentage change year over year and month over month, computed from yearly and monthly mean prices.

## Key results

### Average annual price change (2018–2024)

| Commodity | Avg. change per year (IDR) | Avg. change per year (%) |
|---|---|---|
| Garlic | +3,537 | **+11.70%** |
| Shallots | +2,782 | **+10.90%** |
| Red Chili | +3,885 | +8.21% |
| Sugar | +933 | +6.74% |
| Cooking Oil | +918 | +6.44% |
| Red Cayenne Pepper | +2,221 | +6.15% |
| Chicken Meat | +2,758 | +6.03% |
| Chicken Eggs | +1,721 | +5.20% |
| Green Cayenne Pepper | +1,698 | +4.26% |
| Rice | +488 | +3.75% |

### Average month-over-month change (calendar seasonality)

Computed from the average price of each calendar month across all years, so it describes the typical seasonal shift from one month to the next.

| Commodity | Avg. change per month (%) |
|---|---|
| Garlic | +0.90% |
| Cooking Oil | +0.58% |
| Chicken Eggs | +0.47% |
| Green Cayenne Pepper | +0.40% |
| Sugar | +0.40% |
| Rice | +0.24% |
| Chicken Meat | +0.17% |
| Red Chili | +0.05% |
| Shallots | -0.25% |
| Red Cayenne Pepper | -1.02% |

### Takeaways

- **Garlic and shallots show the strongest inflation** of the group, roughly 3x the growth rate of rice.
- **Rice is the most stable** commodity, with the lowest percentage growth.
- **Red cayenne pepper** has the most negative average monthly change, which may reflect a seasonal price cycle (spikes followed by drops) rather than steady growth; this can be checked with the monthly line plots and boxplots in the notebook.

> Findings are descriptive. The analysis shows patterns in the data and does not establish causes (e.g., weather, supply, or policy effects).

## Limitations and possible next steps

- Add formal time-series decomposition (trend, seasonality, residual) and statistical tests.
- Forecast future prices with ARIMA/SARIMA or Prophet and evaluate on a hold-out period.
- Study event effects such as holidays or the COVID-19 period.
- Convert nominal prices to real (inflation-adjusted) prices.

## Tech stack

Python, Pandas, Matplotlib, Seaborn, SciPy, Jupyter / Google Colab

## How to run

```bash
git clone https://github.com/davinapsh04/food-price-analysis.git
cd food-price-analysis
pip install pandas openpyxl matplotlib seaborn scipy jupyter
jupyter notebook
```

Open the notebook, set the dataset path, and run all cells.

## Repository structure

```
.
├── food-price-analysis.ipynb   # full analysis with outputs and charts
└── README.md
```

Davina Posh, [GitHub](https://github.com/davinapsh04)
