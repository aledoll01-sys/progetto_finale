# Road accidents in Italy

This is my project for the Boolean data analytics course.

## The goal
A company that works in road safety wants to know where to invest. I looked for the Italian municipalities with the most road accidents (in total, per inhabitant and per km²)

## Data
- ISTAT API: accidents, deaths and injured people per municipality, 2001-2024.
- SITUAS: name, population and area of each municipality (2024). I got this data with web scraping.

## What I used
Python (pandas, matplotlib, seaborn, scikit-learn, scipy, statsmodels), Power BI, Git and GitHub.

## Notebooks
1. `01_data_collection` – download the data and understand the columns
2. `02_data_cleaning` – clean the data and join ISTAT and SITUAS
3. `03_eda` – accidents per inhabitant and per km², charts, outliers
4. `04_clustering` – group the municipalities with KMeans
5. `05_statistical_analysis` – ANOVA and a simple forecast

The dashboard is in the `powerbi` folder.

## How to run it
python -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
Then the notebooks.

## Some choices I made
- I checked the meaning of the codes with the official ISTAT numbers.
- In 2024 ISTAT doesn't list municipalities with 0 accidents, so I counted them as 0.
- I used the average of 2022-2024 (the latest years without COVID)
- For rankings and clustering I used only municipalities with at least 10,000 inhabitants,
  because in very small towns a few accidents change the rate a lot.

## What I found
- In Italy there are about 168,000 accidents and 3,000 deaths per year.
- The highest rates per inhabitant are in tourist towns and in cities with many commuters
  (for example Bergamo, Florence, Genoa).
- The Centre and the North have more accidents per inhabitant than the South (confirmed with ANOVA).
- The clustering found 3 groups: high risk per inhabitant, dense urban areas,
  and towns with fewer but more serious accidents.
- The forecast shows a slight decrease, about 167,000 accidents in 2025.

My suggestion: invest first in the "high risk per inhabitant" municipalities of the Centre and North.
