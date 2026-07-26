# spaceX-falcon9
SpaceX Falcon 9 Launch Success Prediction and Data Analysis

IBM Data Science Professional Certificate — Applied Data Science Capstone

Predicting whether a Falcon 9 first-stage booster will land successfully, using public launch data, SQL analysis, geospatial visualization, an interactive dashboard, and supervised machine learning.

Business Problem

SpaceX advertises Falcon 9 launches at $62 million, while competitors charge upward of $165 million — largely because SpaceX recovers and reuses the first stage. If landing outcome can be predicted from public launch data, that cost advantage becomes estimable by anyone, including companies bidding against SpaceX.

Goal: Predict first-stage landing success (Class = 1) or failure (Class = 0) from launch-level features, and identify which factors drive that outcome.

Repository Structure
spacex-falcon9-capstone/
├── README.md
├── notebooks/
│   ├── 01_data_collection_api.ipynb        # SpaceX REST API data collection
│   ├── 02_data_wrangling.ipynb             # Cleaning, feature engineering, target label
│   ├── 03_eda_visualization.ipynb          # Matplotlib/Seaborn exploratory analysis
│   ├── 04_eda_sql.ipynb                    # SQL queries against the launch records
│   ├── 05_folium_launch_sites.ipynb        # Geospatial launch site analysis
│   └── 06_ml_prediction.ipynb              # Classification model comparison
├── dash_app/
│   └── spacex_dash_app.py                  # Interactive Plotly Dash dashboard
├── data/
│   ├── raw/                                # Raw collected data
│   └── cleaned/                            # Wrangled, model-ready data
└── presentation/
    └── SpaceX_Falcon9_Capstone_Report.pdf  # Final capstone presentation
Methodology
Stage	What was done
Data Collection	Pulled structured launch records from the SpaceX REST API; scraped Wikipedia's Falcon 9 launch tables with BeautifulSoup for outcome details not in the API
Data Wrangling	Handled missing payload values, standardized booster naming, engineered the binary Class target from 9 raw outcome categories
EDA & Visualization	Analyzed success rate by launch site, orbit, payload mass, and flight number using Seaborn
EDA with SQL	Queried the launch dataset directly (site counts, payload aggregates, outcome breakdowns)
Geospatial Analysis	Mapped all launch sites with Folium; calculated proximity to coastlines
Interactive Dashboard	Built a Plotly Dash app with site/payload filters, pie chart, and scatter plot
Predictive Modeling	Trained and tuned Logistic Regression, SVM, Decision Tree, and KNN classifiers with GridSearchCV (10-fold CV)
Key Results
Overall landing success rate: 66.7% across all Falcon 9 launches analyzed
Landing success rate rose sharply after 2015 as SpaceX gained flight experience
Best model: Decision Tree, with 86.25% cross-validated accuracy (all four models scored 83.3% on the held-out test set)
Launch site and orbit type both show measurable differences in landing success rate
Tools Used

Python · Pandas · NumPy · Matplotlib · Seaborn · SQL (SQLite) · Folium · Plotly Dash · scikit-learn

How to Run
Clone this repo: git clone https://github.com/yourusername/spacex-falcon9-capstone.git
Install dependencies: pip install pandas numpy matplotlib seaborn folium scikit-learn ipython-sql sqlalchemy wget dash
Open notebooks in order (01 → 06) in Jupyter or Google Colab and run all cells
To launch the dashboard: python dash_app/spacex_dash_app.py
Presentation

Full capstone report (PDF): presentation/SpaceX_Falcon9_Capstone_Report.pdf

Author

SAMAVIA YASIN  IBM Data Science Professional Certificate — Capstone Project, 2026
