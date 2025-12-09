# Predicting-Flight-Delays-Proposing-Operational-Improvements-using-Machine-Learning
Airline operations are highly sensitive to delays, which can cascade across the network and cost millions annually. This project uses real U.S. flight data (BTS On-Time Performance dataset) to predict departure delays, identify root causes, segment airports, and recommend data-driven interventions.

The project demonstrates end-to-end analytical thinking:
• Data ingestion + cleaning + feature engineering
• Exploratory analysis (EDA) to identify patterns
• ML models: Random Forest, XGBoost, Gradient Boosting, Logistic Regression
• Unsupervised learning: Clustering airports by delay patterns
• Business recommendations tied to operational strategy
• Optionally deployable via Streamlit + AWS SageMaker

## Project Structure
```
flight-delay-ml/
│
├── data/                     # Raw + cleaned datasets
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── 04_modeling.ipynb
│   ├── 05_clustering.ipynb
│   └── 06_dashboard_app.ipynb
│
├── src/
│   ├── preprocess.py
│   ├── train_model.py
│   ├── inference.py
│   └── utils.py
│
├── app/
│   └── streamlit_app.py
│
├── README.md
└── requirements.txt
```

Dataset: https://transtats.bts.gov/ONTIME/Airline.aspx
