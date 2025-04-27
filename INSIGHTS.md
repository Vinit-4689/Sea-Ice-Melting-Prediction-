# 📈 Project Insights and Learnings

## 🌐 Introduction
In this project, we aimed to forecast the Arctic Sea Ice Extent over the next 20 years using historical data from 1979 to 2025. We performed comprehensive data cleaning, exploratory data analysis (EDA), modeling with multiple approaches, evaluation, and professional visualization.

---

## 🔍 Exploratory Data Analysis (EDA)

### Key Observations:
- **No missing values** were found, making preprocessing straightforward.
- **Clear declining trend** in sea ice extent from 1979 to 2025.
- **Variability:** Annual fluctuations were visible but the overall trend was downward.
- **Recent years** showed sharper and faster declines, suggesting accelerating ice loss.

### Insights:
- A strong and consistent **negative trend** over decades was detected.
- Seasonal cycles were **not heavily captured** since we used annual/monthly mean data.
- Data was not stationary initially — trend needed to be handled for time series modeling.

---

## 📊 Modeling Approaches and Learnings

### 1. Polynomial Regression
- Fitted a polynomial curve to the extent data.
- **Pros:**
  - Very good historical fit (R² ≈ 0.81, RMSE ≈ 0.250)
- **Cons:**
  - **Unrealistic future forecast** — polynomial curves tend to "blow up" outside training data, predicting sharp upward trends in this case.

**Learning:**
> Polynomial models can fit history well but fail in forecasting, especially without physical constraints.

---

### 2. ARIMA (1,1,1) Model
- Built after differencing the data to achieve stationarity.
- Manual (p,d,q) selection due to `auto_arima` incompatibility.
- **Pros:**
  - Predicts relatively stable future (no blow-up).
- **Cons:**
  - Poor historical fit (R² = -16.5, RMSE = 2.40)
  - Captures less variability and does not match historical fluctuations well.

**Learning:**
> ARIMA can be too simple without optimal tuning, resulting in poor performance on complex trends.

---

### 3. Prophet Model (Facebook)
- Trained with automatic trend detection and forecasted future.
- **Pros:**
  - Very good historical fit (R² ≈ 0.808, RMSE ≈ 0.251)
  - Captures long-term trend accurately.
- **Cons:**
  - Forecasts **unrealistic negative values** in long-term future.
  - Required **clipping** at 0 to ensure physical realism (sea ice cannot go negative).

**Learning:**
> Prophet models trends and uncertainty well but needs manual constraint handling when dealing with physical quantities like ice extent.

---

## 👩‍💻 Overall Learnings
- **EDA is critical** to understanding data behavior before modeling.
- **Stationarity** is vital for time series forecasting models like ARIMA.
- **Polynomial models** fit data but extrapolate poorly.
- **ARIMA models** predict stable futures but need careful tuning.
- **Prophet models** automate trend + uncertainty capture but must be adapted to physical constraints.
- **Real-world constraints** (like "no negative ice") must always be applied post-modeling.

---

# 🌟 Final Conclusion
Prophet (with clipping) provided the best overall forecast for Arctic sea ice extent, balancing historical fit and realistic future projections.

**The project demonstrates full-cycle data science capabilities:**
from data cleaning → EDA → modeling → evaluation → final professional packaging.

---

# 👏 Thank you for reading!

