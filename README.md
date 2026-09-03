# Zomato Delivery Analysis — EDA

An end-to-end exploratory data analysis project on Zomato's food delivery dataset, covering data cleaning, feature engineering, univariate/bivariate analysis, and statistical hypothesis testing to understand what drives delivery time.

## Objective

To explore the factors that influence food delivery time — distance, traffic, weather, festivals, rider attributes, and order load — and validate observed patterns using statistical tests rather than visual inspection alone.

## Dataset

The raw dataset (`Zomato Dataset.csv`) contains delivery-level records with:
- Delivery person details (age, ratings, vehicle type & condition)
- Restaurant and delivery location coordinates
- Order details (type of order, time ordered, time picked up)
- Contextual conditions (weather, road traffic density, festival, city type)
- Target variable: delivery time taken (in minutes)

## Project Workflow

| Notebook | Description |
|---|---|
| `01_exporting_data.ipynb` | Initial data load and inspection |
| `02_cleaning_preprocessing.ipynb` | Handling missing values, fixing inconsistent formats (e.g. time columns), and data type corrections |
| `03_feature_eng_EDA.ipynb` | Feature engineering — converting raw lat/long into `distance_km` (haversine formula), extracting date/time features (`order_hour`, `time_of_day`, `is_weekend`, `order_day_of_week`), and deriving `pickup_delay_min`, `age_group`, `rating_category`, `distance_bucket` |
| `04_univariate_bivariate_eda.ipynb` | Univariate distributions and bivariate relationships between features and delivery time, using histograms, boxplots, and correlation heatmaps |
| `05_stats_tests.ipynb` | Statistical hypothesis testing — t-tests, Mann-Whitney U, chi-square tests of independence, and correlation significance testing to confirm which observed patterns are statistically meaningful |

## Key Files

- `Zomato Dataset.csv` — original raw dataset
- `cleaned_zomato.csv` — output after cleaning/preprocessing
- `zomato_dataset_Engineered.csv` — final dataset with engineered features, used for EDA and statistical testing

## Key Insights

- **Order load and traffic are the strongest drivers of delivery time** — deliveries with multiple stacked orders and heavy ("Jam") traffic show the largest increases in delivery time.
- **Festivals significantly slow down deliveries**, nearly doubling average delivery time compared to non-festival days.
- **Weather conditions matter** — cloudy and foggy conditions are associated with noticeably longer delivery times than sunny conditions.
- **Distance has a moderate but real relationship** with delivery time, as expected.
- **Day of week (weekend vs weekday) shows no significant effect** on delivery time.
- **Vehicle condition and delivery person ratings** show meaningful associations with delivery speed.

## Tools & Libraries

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- SciPy (statistical testing)
