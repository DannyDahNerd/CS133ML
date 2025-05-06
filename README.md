# Electric Vehicle Market Analysis in Washington

## Overview
This project analyzes electric vehicle (EV) registration data in Washington State to explore trends in pricing, efficiency, and geographic distribution. Using a combination of data cleaning, visualization, and machine learning, the study aims to uncover insights into EV adoption and predict vehicle characteristics such as MSRP category, electric range, and purchase location.

## Goals
- Clean and preprocess EV registration data with substantial missing values.
- Explore historical and manufacturer-level trends in price, efficiency, and adoption.
- Use machine learning to:
  - Classify MSRP tiers.
  - Predict vehicle electric range.
  - Predict purchase coordinates.

## Dataset
- Source: Washington State Department of Licensing EV Registration Data
- Features used: Make, Model, Year, Electric Range, MSRP, Vehicle Type, CAFV Eligibility, Coordinates, etc.
- Major issues addressed:
  - 99% missing MSRP values
  - 50%+ missing electric range values
  - Manual reference-based imputation for missing data

## Key Questions & Visualizations
1. **How has the average MSRP of EVs changed over time?**
2. **How has EV adoption changed annually?**
3. **How do different manufacturers affect annual registration counts?**
4. **Which manufacturers offer the most affordable vehicles each year?**
5. **How efficient are vehicles in terms of range vs. price?**

## Machine Learning Models
| Model | Task | Type | Performance |
|-------|------|------|-------------|
| RandomForestClassifier | MSRP tier prediction | Classification | ~94% accuracy |
| RandomForestRegressor | Predict coordinates | Regression | ~20–30 mile RMSE |
| RandomForestRegressor | Predict range | Regression | ~4.4 mile RMSE |

- Preprocessing done using pipelines (StandardScaler + OneHotEncoder)
- Feature engineering and categorical binning for MSRP categories
- Hyperparameter tuning using `HalvingRandomSearchCV`

## Requirements

Install the following dependencies using pip or conda:

```
pip install pandas numpy scikit-learn matplotlib seaborn plotly
```

Jupyter Notebook is recommended to run the analysis:
```
pip install notebook
```

## File Structure

```
.
├── EVProject_Final.ipynb                   # Full notebook with code and models
├── MSRPFinal.csv                            # MSRP Values
├── 0range.csv                               # Electric Vehicles with 0 Range filled
├── Electric_Vehicle_Population_Density   # Original Data file (google drive as too big for git)
├── README.txt                                # Project documentation
```

## Authors
- Patrick Le
- Daniel Ly

CS133, Spring 2025  
San Jose State University

## References
- EPA GHG Emissions Data: https://www.epa.gov/ghgemissions/sources-greenhouse-gas-emissions
- Electric Vehicle Myths: https://www.epa.gov/greenvehicles/electric-vehicle-myths
- Visual Capitalist EV Adoption Map: https://www.visualcapitalist.com/mapped-electric-vehicle-adoption-by-state/
