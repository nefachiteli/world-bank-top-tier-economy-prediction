# Predicting Top-Tier Economies from World Bank Indicators

## Motivation
The World Bank tracks GDP and population for nearly every country in the
world every year. This project asks: **using only a country's population
size and how fast its population and economy are growing without
looking at its GDP level directly can we predict whether it belongs to
the top 25% of economies (by GDP per capita) in a given year? And does
the model make that call fairly across different world regions?**

The project follows the **CRISP-DM** process: exploratory data analysis,
data cleaning/merging, model training/evaluation and prediction on a
new scenario.

## Data
[World Bank Databank](https://databank.worldbank.org/); GDP and
population by country, 2000–2023 (Credit and Economic Data category).

- `data/gdp.csv` - GDP (current US$) by country and year, World Bank
  national accounts data.
- `data/population.csv` - total population by country and year.
- `data/country-codes.csv` - ISO country reference table used to attach
  each country's continent/region and to filter out World Bank's
  aggregate rows (e.g. "World", "Euro area"), keeping only real
  countries.

## Libraries Used
- `pandas`, `numpy` - data handling
- `matplotlib`, `seaborn` - visualization
- `scikit-learn` - model training, encoding, and evaluation
