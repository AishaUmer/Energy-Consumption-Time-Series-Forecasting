# Energy-Consumption-Time-Series-Forecasting
## 📌 Task Objective
The objective of this project is to forecast short‑term hourly household energy usage using historical power consumption data. The goal is to transform raw minute‑level measurements into a clean, structured time series and apply forecasting models to understand and predict energy usage patterns. This supports better energy planning, smart‑home automation, and consumption optimization.

---

## 🧠 Your Approach
### **1. Data Loading & Parsing**
Loaded the Household Power Consumption dataset.
Combined Date and Time into a single datetime index.
Selected Global_active_power as the target variable for forecasting.

### **2. Data Cleaning**
Replaced invalid entries ("?") with NaN.
Converted all numeric columns to float using safe coercion.
Removed rows with missing or corrupted values.
Ensured the time index was continuous and properly formatted.

### **3. Time‑Series Resampling**
Resampled minute‑level data into hourly average energy usage.
Applied time‑based interpolation to fill small gaps.
Created a smooth, consistent hourly time series suitable for forecasting.

### **4. Feature Engineering**
Extracted meaningful time‑based features:
Hour of day
Day of week
Weekend indicator

### **5. Forecasting Models**
Implemented two forecasting models:
ARIMA
Classical time‑series model capturing trends and autocorrelation.
Works well on smooth hourly data.

### **XGBoost Regressor**
Machine‑learning model using engineered features.
Learns nonlinear relationships between time‑based patterns and energy usage.

### **6. Evaluation & Visualization**
Evaluated models using MAE and RMSE.
Plotted actual vs. predicted hourly energy usage for comparison.
Compared how each model responds to daily and weekly consumption patterns.
These features help machine‑learning models capture daily and weekly patterns.

---

## 📊 Results and Findings
### **1. Clear Daily Usage Patterns**
Energy usage peaks during morning and evening hours, reflecting typical household activity cycles.

### **2. Weekend Behavior Differs**
Consumption patterns on weekends are more irregular, and the is_weekend feature helped XGBoost capture this variation.

### **3. ARIMA Captures Overall Trend**
ARIMA performed well on the smoothed hourly data, modeling the general trend but reacting slowly to sudden changes.

### **4. XGBoost Learns Feature‑Driven Patterns**
XGBoost outperformed ARIMA in capturing:
Hour‑based variations
Day‑of‑week effects
Weekend differences

### **5. Both Models Track Real Usage**
The forecast visualization shows that both ARIMA and XGBoost follow the actual energy usage curve, with XGBoost adapting more quickly to fluctuations.

##
