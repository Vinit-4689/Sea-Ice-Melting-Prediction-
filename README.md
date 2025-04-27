# Sea Ice Extent Forecasting Project 🌎❄️

## 📑 Objective:
Forecast Arctic Sea Ice Extent over the next 20 years using time series analysis methods.

---

## 📊 Dataset:
- **Source:** [National Snow and Ice Data Center (NSIDC)](https://nsidc.org/)
- **Data:** Monthly Sea Ice Extent (1979-2025)
- **File:** `N_03_extent_v3.0.csv`

---

## 🔥 Models Built:
1. **Polynomial Regression**
2. **ARIMA (1,1,1) Model**
3. **Prophet Model**

---

## 🧐 Exploratory Data Analysis:
- Identified a clear **declining trend** in sea ice extent over the years.
- Recent years show a sharper and faster decline.

---

## 📈 Model Evaluations:

| Model | RMSE | R² | Comments |
|:------|:-----|:--|:---------|
| Polynomial Regression | 0.250 | 0.810 | Great historical fit, unrealistic future |
| ARIMA (1,1,1) | 2.402 | -16.510 | Poor fit, flat future |
| Prophet | 0.251 | 0.808 | Good fit, realistic trend with clipping |

---

## 🏆 Final Model Selected:
- **Prophet Model (with clipping)**
- Forecasts a realistic slow decline in sea ice extent.

---

## 📂 Project Structure:
```
data/         # Dataset
notebooks/    # EDA + Modeling
outputs/      # Saved Plots
README.md     # Project report
requirements.txt # Libraries used
```

---

## 🛠️ Tools and Libraries Used:
- Python
- Pandas
- Matplotlib / Seaborn
- Scikit-learn
- Statsmodels (ARIMA)
- Prophet (Facebook)
- Numpy

---

## 📈 Final Forecast Plot:
(Insert "Prophet clipped forecast" image here!)

---

## 📢 Key Learnings:
- Importance of stationarity in time series modeling.
- Why polynomial models can overfit.
- How Prophet automatically handles trend and uncertainty.
- Importance of applying real-world constraints (e.g., clipping).

---

## 📬 Contact

**Vinit Singh Pathir**  
[LinkedIn](https://www.linkedin.com/in/vinit-singh-cse/)  
Feel free to reach out if you want to collaborate on remote sensing, data science, or climate projects!


## 🌍 License

This project is open-source and free to use under the MIT License.

---

# 🚀 Thank you for visiting the project!

