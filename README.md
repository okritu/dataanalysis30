# Zomato Restaurant Data Analysis

Exploratory data analysis on a dataset of restaurant listings from Zomato. The
project looks at restaurant types, customer votes, rating distribution, cost
for two people, and whether online ordering availability relates to rating.

## Dataset

The script expects a CSV file named `Zomato-data-.csv` placed in a `data/`
folder at the project root:

```
zomato-analysis/
├── data/
│   └── Zomato-data-.csv
├── zomato_analysis.py
└── ...
```

Relevant columns used in this analysis:

| Column                          | Description                                  |
|----------------------------------|-----------------------------------------------|
| `rate`                           | Rating, e.g. `4.1/5`                          |
| `votes`                          | Number of votes the restaurant received       |
| `approx_cost(for two people)`    | Approximate cost for two people               |
| `listed_in(type)`                | Restaurant category (Dine-out, Delivery, etc.)|
| `online_order`                   | Whether online ordering is available          |

If you don't already have the dataset, a similarly-structured version is
commonly available on [Kaggle](https://www.kaggle.com/datasets) — search for
"Zomato restaurants dataset."

## Setup

```bash
git clone <this-repo-url>
cd zomato-analysis
pip install -r requirements.txt
```

## Usage

```bash
python zomato_analysis.py
```

The script:
1. Loads the CSV from `data/Zomato-data-.csv`
2. Cleans the `rate` column (converts `"4.1/5"` → `4.1`)
3. Generates five plots, saved to an `output/` folder:
   - `restaurant_types.png` — count of restaurants per listing type
   - `votes_by_type.png` — total votes received per restaurant type
   - `rating_distribution.png` — histogram of ratings
   - `cost_distribution.png` — distribution of approximate cost for two
   - `online_order_vs_rating.png` — boxplot of rating by online order availability

Plots are saved as PNG files rather than displayed interactively, so the
script can also run headlessly (e.g. in CI or a server without a display).

## Key Findings

- The majority of restaurants in the dataset fall into the dine-out category.
- Dine-out restaurants also receive the highest total number of votes.
- Most ratings cluster between roughly 3.5 and 4.0.
- Restaurants that *don't* offer online ordering tend to have lower median
  ratings than those that do.

## Project Structure

```
zomato-analysis/
├── data/                   # place Zomato-data-.csv here (not tracked in git)
├── output/                 # generated plots (created on run)
├── zomato_analysis.py      # main analysis script
├── requirements.txt
└── README.md
```

## License

This project is provided for educational/portfolio purposes.
