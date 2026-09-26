# upskillcampus
EDUnet upskill Internship Project


# Crop Yield Prediction using Machine Learning

Final project — Data Science & Machine Learning Internship, Uniconverge Technologies (UCT), via Edunet Foundation.

## Problem
Predict crop yield (Quintal/Hectare) from cultivation cost data across Indian crops and states.

## Dataset
The internship brief described one unified table (Crop, Variety, State, Quantity, Production, Season, Unit, Cost, Recommended Zone). The actual files provided are 5 separate tables at different levels of detail and do not merge into one. This project uses `datafile (1).csv` — the only file with a clean crop x state cost/yield structure (49 rows). The other 4 files are not used in the model.

## Repo structure
```
.
├── datafile (1).csv          # cultivation cost + yield — used for modeling
├── datafile (2).csv          # national production data — not used
├── datafile (3).csv          # crop variety reference — not used
├── datafile.csv              # national price index — not used
├── produce.csv                # macro agriculture stats — not used
├── Prediction_of_Agriculture_Crop_Production_in_India.py
├── Crop_Yield_Prediction_Final_Report.docx
├── Crop_Yield_Prediction_Final_Report.pdf
└── README.md
```

## How to run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn python-docx
python Prediction_of_Agriculture_Crop_Production_in_India.py
```

## Approach
1. Load and clean all 5 files (strip column names, handle missing values).
2. EDA on the cultivation dataset — crop distribution, cost/yield boxplots, correlation heatmap.
3. Encode Crop and State; features = Crop, State, Cost of Cultivation (A2+FL), Cost of Cultivation (C2); target = Yield.
4. Train/test split (80/20), Random Forest Regressor (100 estimators).
5. Evaluate with MSE and R²; extract feature importance.

## Results
| Metric | Value |
|---|---|
| MSE | 5601.27 |
| R² | 0.94 |

Top features: Cost of Cultivation C2 (48.3%), Cost of Cultivation A2+FL (38.1%), Crop (12.2%), State (1.4%).

## Report
Full report with methodology, EDA charts, and results: `Crop_Yield_Prediction_Final_Report.pdf` / `.docx`.
