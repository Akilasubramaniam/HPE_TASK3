 **KPI Forecasting & Energy-Saving Window Detection**

This project forecasts network KPIs (Avg_UE_Number and DL_Prb_Utilization) using Random Forest and Prophet models and identifies energy-saving time windows based on configurable thresholds.

 **Input Data**
DL_Prb_Utilization_Data.csv
Avg_UE_Number_Data.csv
Includes data for 6 different NCI cells.

**Machine Learning Models Used**
Random Forest Regressor
Facebook Prophet

Each model is trained separately for each KPI and NCI.
R² scores are printed for performance comparison.

**Configurable Parameters**
ES_MODES (Energy Saving Modes):
Conservative
Moderate(default)
Aggressive

Window Size: Adjustable (default: 30 mins)

**Outputs**
6mo_KPI_RF_forecast.csv – 6-month forecast using Random Forest
6mo_KPI_Prophet_forecast.csv – 6-month forecast using Prophet
Energy_Saving_Windows_Moderate.csv – Filtered windows based on KPI thresholds

 **How It Works**
Merges KPI data on timestamp & NCI.
Forecasts both KPIs for the next 6 months.
Filters values within selected ES mode ranges.
Groups into continuous 15-min intervals and extracts those ≥ window size.
Saves all results as CSVs.

 **Evaluation**
Random Forest R² Score: Printed in console

Prophet R² Score: Printed in console

**Requirements**
pandas, numpy, sklearn, prophet, matplotlib

**Run the Code**

python forecast.py
