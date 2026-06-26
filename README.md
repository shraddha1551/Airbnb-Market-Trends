# Airbnb NYC Market Trends Analysis

> An exploratory data analysis of New York City Airbnb listings — uncovering pricing patterns, room type distributions, neighbourhood trends, and review activity over time.

---

## Project Overview

This project performs end-to-end **Exploratory Data Analysis (EDA)** on a large Airbnb NYC dataset (~102,000 listings). The goal is to extract meaningful insights about the short-term rental market in New York City, covering data cleaning, visualisation, and pattern discovery.

---

## Dataset

- **Source:** Airbnb NYC open dataset (`compressed_data.csv.gz`)
- **Size:** ~102,599 records, 26 columns
- **Key Features:**
  | Column | Description |
  |---|---|
  | `NAME` | Listing title |
  | `neighbourhood group` | Borough (Manhattan, Brooklyn, etc.) |
  | `room type` | Entire home, Private room, or Shared room |
  | `price` | Nightly price in USD |
  | `service fee` | Additional service fee |
  | `minimum nights` | Minimum stay requirement |
  | `number of reviews` | Total reviews received |
  | `last review` | Date of most recent review |
  | `availability 365` | Days available per year |
  | `Construction year` | Year the property was built |

---

## Tech Stack

- **Language:** Python 3
- **Libraries:**
  - `pandas` — data manipulation and cleaning
  - `numpy` — numerical operations
  - `matplotlib` — static visualisations
  - `seaborn` — statistical data visualisation

---

## Data Cleaning Steps

1. **Handled missing values:**
   - Filled `reviews per month` nulls with `0` (no reviews = 0 per month)
   - Filled `last review` nulls with the earliest date in the dataset
   - Dropped rows missing `NAME` and `host name` (core listing identity)
   - Dropped `license` and `house_rules` columns (>99% and ~51% missing respectively)

2. **Type conversions:**
   - Parsed `last review` as `datetime`
   - Stripped `$` and `,` from `price` and `service fee`, converted to `float`

3. **Removed duplicates:** Dropped fully duplicate rows

4. **Final dataset:** ~101,410 clean records across 24 columns

---

## Key Visualisations & Insights

### 1. Distribution of Listing Prices
The histogram reveals a fairly **uniform spread of prices** across the $50–$1,200 range, with no single price point dominating. The KDE curve confirms this even distribution.

### 2. Room Type Distribution
- **Private rooms** and **Entire home/apt** are the dominant listing types
- Shared rooms make up a small minority of listings

### 3. Listings by Neighbourhood Group
- **Manhattan** and **Brooklyn** account for the majority of listings
- Staten Island has the fewest listings by a significant margin

### 4. Price vs. Room Type (Box Plot)
- Entire home/apt listings command the highest median price
- Shared rooms are the most affordable
- All room types show significant price outliers

### 5. Reviews Over Time
- Review activity peaked around **2019** before declining, likely reflecting post-pandemic shifts in travel behaviour
- A sharp spike in reviews is visible in the late 2018–2019 period, suggesting high platform engagement

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/shraddha1551/Airbnb-Market-Trends.git
cd Airbnb-Market-Trends

# Install dependencies
pip install pandas numpy matplotlib seaborn

# Launch the notebook
jupyter notebook
```

Open the `.ipynb` file and run cells top to bottom.

---

## Project Structure

```
Airbnb-Market-Trends/
│
├── compressed_data.csv.gz       # Raw dataset
├── airbnb_eda.ipynb             # Main analysis notebook
└── README.md                    # Project documentation
```

---

## Summary of Findings

| Insight | Detail |
|---|---|
| **Most popular borough** | Manhattan |
| **Most common room type** | Private room |
| **Average nightly price** | ~$625 |
| **Average service fee** | ~$125 (~20% of price) |
| **Review activity peak** | 2018–2019 |
| **Typical minimum stay** | 3 nights (median) |

---

## Future Scope

- Sentiment analysis on listing names and house rules
- Geospatial mapping of listings by price and neighbourhood
- Predictive modelling for pricing optimisation
- Anomaly detection for fraudulent or outlier listings

---

## Author

**Shraddha**  
B.Tech Computer Science | SRM IST  
[GitHub](https://github.com/shraddha1551)

---

## 📄 License

This project is for educational and portfolio purposes. Dataset sourced from publicly available Airbnb data.
