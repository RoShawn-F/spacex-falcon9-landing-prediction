# SpaceX Falcon 9 Landing Prediction 🚀

> *It's not a phase, it's a pipeline.*

An end-to-end data science project that predicts whether a SpaceX Falcon 9 first stage will land successfully. SpaceX advertises Falcon 9 launches at about **$62 million**, while other providers charge **$165 million or more**, and much of that gap comes from reusing the first stage. Predicting a successful landing therefore helps estimate the cost of a launch, the kind of insight a competing launch provider could use when bidding against SpaceX.

The project follows the full data pipeline: collecting data from an API and by web scraping, cleaning it, exploring it with SQL and visualizations, building an interactive dashboard and maps, and training classification models.

✅ **Complete.** All nine stages are finished; notebooks below include their outputs.

---

## Project Roadmap

| # | Stage | What it covers | Status |
|---|---|---|---|
| 1 | [Data collection (API)](jupyter-labs-spacex-data-collection-api.ipynb) | Pull launch data from the SpaceX REST API | ✅ Done |
| 2 | [Data collection (web scraping)](jupyter-labs-webscraping.ipynb) | Scrape Falcon 9 launch records from Wikipedia | ✅ Done |
| 3 | [Data wrangling](labs-jupyter-spacex-Data_wrangling-v2.ipynb) | Clean the data and create the landing outcome label | ✅ Done |
| 4 | [EDA with SQL](jupyter-labs-eda-sql-coursera_sqllite.ipynb) | Query launch records to find patterns | ✅ Done |
| 5 | [EDA with visualization](jupyter-labs-eda-dataviz-v2.ipynb) | Explore relationships between payload, orbit, launch site and success | ✅ Done |
| 6 | [Geospatial analysis (Folium)](lab-jupyter-launch-site-location-v2.ipynb) | Map launch sites and their surroundings | ✅ Done |
| 7 | [Interactive dashboard (Plotly Dash)](spacex_dash_app.py) | Explore success rates by site and payload | ✅ Done |
| 8 | [Predictive analysis](SpaceX-Machine-Learning-Prediction-Part-5-v1.ipynb) | Compare classification models (Logistic Regression, SVM, Decision Tree and more) | ✅ Done |
| 9 | Final presentation | Summarize findings for stakeholders | ✅ Done |

> 🗺️ GitHub can't display interactive Folium maps. [View the maps on nbviewer](https://nbviewer.org/github/RoShawn-F/spacex-falcon9-landing-prediction/blob/main/lab-jupyter-launch-site-location-v2.ipynb).

## Results

| Model | Validation accuracy (10-fold CV) | Test accuracy (18 launches) |
|---|---|---|
| Logistic Regression | 84.6% | 83.3% |
| SVM | 84.8% | 83.3% |
| **Decision Tree** | **88.9%** | **83.3%** |
| KNN | 84.8% | 83.3% |

**Best model:** Decision Tree (highest cross-validation accuracy). All four models score 83.3% on the held-out launches; the main error is false positives (predicting a landing that failed).

**Key findings**

- Landing success rose from 0% (2010–2013) to about 90% (2019) as SpaceX gained experience.
- KSC LC-39A has the best success rate: 10 of 13 launches landed.
- 2,000–5,000 kg payloads on FT and B4 boosters land most often; v1.0/v1.1 boosters rarely landed.
- SSO and VLEO orbits land reliably; GTO is the hardest (52%).
- Launch sites sit close to the coast, railways and highways, but far from cities (VAFB SLC-4E: coastline 1.35 km, Santa Maria 39 km).

> Note: the live SpaceX API no longer returns JSON, so the data-collection notebook uses IBM's saved copy of the API response.

## Tools

Python · pandas · NumPy · Requests · BeautifulSoup · SQL · Matplotlib · Seaborn · Folium · Plotly Dash · scikit-learn · Jupyter

---

*Completed as the Applied Data Science Capstone, the final course in the IBM Data Science Professional Certificate on Coursera.*
