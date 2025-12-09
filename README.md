# Flight Delay Prediction – United Airlines (JFK, 2011) using Machine Learning

## Project Overview
This project analyzes **United Airlines (UA) flights from JFK Airport in 2011** to identify the main factors contributing to **departure delays** and to build a **machine learning model** that predicts flight delays. Using historical data on departures, arrivals, cancellations, and diversions, the project demonstrates how **data-driven insights** can help airlines optimize scheduling, reduce delays, and improve operational efficiency.

---

## Datasets
Four datasets are used in this project:

1. **Departures:** Scheduled vs. actual departure times, delay reasons, taxi-out times, etc.  
2. **Arrivals:** Scheduled vs. actual arrival times, delays, and taxi-in times.  
3. **Cancellations:** Records of cancelled flights.  
4. **Diversions:** Records of diverted flights.  

**Source:** [BTS TranStats – On-Time Performance](https://transtats.bts.gov/ONTIME/)  
**Scope:** JFK Airport, United Airlines, 2011 (January–December)

---

## Features
The dataset contains 28 key features including:

- Flight operational metrics: `Scheduled/Actual Departure`, `Elapsed Time`, `Taxi-Out Time`  
- Delay reasons: `Delay Carrier`, `Delay Weather`, `Delay NAS`, `Delay Security`, `Delay Late Aircraft Arrival`  
- Time features: `Month`, `DayOfWeek`, `Hour`  
- One-hot encoded features: `DayOfWeek_*`, `Destination Airport_SFO`  
- Targets: `is_delayed` (departure delay), `is_arrival_delayed`  

> Full column descriptions with business insights are provided in the notebook.

---

## Machine Learning Model
- **Algorithm:** Random Forest Classifier  
- **Hyperparameter Optimization:** GridSearchCV  
- **Train/Test Split:** 80/20  
- **Evaluation Metric:** F1-score (optimized for imbalanced classes)  

---

## Results

**Model Performance:**

- **Accuracy:** 97.6%  
- **Confusion Matrix:**

| Actual \ Predicted | On-Time | Delayed |
|-------------------|---------|---------|
| **On-Time**       | 782     | 0       |
| **Delayed**       | 19      | 92      |

**Top Predictive Features (Optimized Model):**

| Feature                         | Importance | Business Insight |
|---------------------------------|-----------|----------------|
| **ActualDepartureHour**          | 28%       | Flights leaving at certain hours are more likely to be delayed — schedule adjustments could reduce delays. |
| **Delay Carrier (Minutes)**      | 12%       | Airline operational delays are significant — focus on turnaround efficiency. |
| **Delay National Aviation System** | 9.4%     | System-level delays matter — coordination with air traffic authorities may help. |
| **ScheduledDepartureHour**       | 9.3%      | Original schedule impacts delays — adjusting departure windows could help. |
| **Taxi-Out time (Minutes)**      | 6.7%      | Ground operations affect delays — gate/taxi efficiency improvements are impactful. |

---

## Insights & Trends

**Monthly Delays:**  
- Peak in July (22.8%), May (17.9%), and June (15.9%)  
- Lowest in November (3.1%), March (5%), and February (5.6%)  

**Day-of-Week Delays:**  
- Highest on Saturday (14.8%) and Monday (13.5%), lowest on Sunday (10.8%)  

**Hourly Delays (ScheduledDepartureHour):**  
- Early morning flights (<7 AM) rarely delayed (<2%)  
- Evening flights (7–8:30 PM) have delays reaching 30–40%  

**Business Implications:**  
1. Adjust flight schedules to reduce peak-hour delays  
2. Improve operational efficiency for carrier and ground operations  
3. Allocate resources for high-delay months and days  
4. Coordinate with NAS authorities to reduce system-level delays  

---

## Visualizations
- Feature Importance (Top 15 features driving delays)  
- Confusion Matrix  
- Hourly Delay Trends  
- Monthly & Day-of-Week Delay Trends  

These visualizations provide actionable insights for **operations, planning, and scheduling**.

---

## Repository Contents
- `Flight_Delay_Analysis.ipynb` – Main notebook with full analysis, ML model, and visualizations  
- `Detailed_Statistics_Departures.csv`, `Detailed_Statistics_Arrivals.csv`, `Detailed_Statistics_Cancellations.csv`, `Detailed_Statistics_Diversions.csv` – Raw datasets  

---

## Conclusion
This project demonstrates how **machine learning combined with historical flight data** can identify **key drivers of delays** and provide **actionable insights** for airlines. The model achieves **high accuracy** and highlights operational patterns that can help **reduce delays, improve efficiency, and enhance customer satisfaction**.
