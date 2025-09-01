# 📑 **Progress Summary — AI + Meteorology Learning Journey (Up to Week 2, Day 1)**

---

## 🧭 **Big Picture Goal**

I am on a **30-day roadmap** to learn **AI + meteorology coding** with real climate datasets.
The end goal: build skills and a working prototype that shows how **AI can support NIMET’s operations** (airport weather, climate monitoring, anomaly detection).

---

## ✅ **Steps You’ve Completed So Far**

### **Week 1: Foundations**

1. **Environment Setup**

   -  Created a Jupyter workspace (`weather-ai` folder).
   -  Activated a virtual environment.
   -  Installed scientific Python libraries: `xarray`, `netCDF4`, `matplotlib`, `pandas`.
   -  📌 **Skill gained**: Scientific Python project setup.

2. **Dataset Familiarization**

   -  Opened **NOAA tmin.2025.nc** (daily minimum temperature for 2025).
   -  Inspected dataset structure: dimensions (`time, lat, lon`), variables (`tmin`), attributes (units, source).
   -  Learned that time was encoded in **CFTime** format (not standard Python datetime).
   -  📌 **Skill gained**: Understanding **NetCDF metadata** and time encodings.

3. **First Time Series Extraction**

   -  Extracted Tmin for a single location (first Abuja, later Asaba).
   -  Converted **CFTime → datetime64** for clean plotting.
   -  Plotted **daily Tmin vs Time** for the year 2025.
   -  Saved figure as `.png`.
   -  📌 **Skill gained**: Extracting and visualizing climate time series.

---

### **Week 2 (So Far)**

#### **Day 1: Time Series at a Location**

-  Selected **Asaba** coordinates (`lat=6.2, lon=6.7`).
-  Plotted the **entire year’s Tmin series**.
-  Formatted the x-axis to show months (`Jan, Feb, ...`).
-  Produced figure: `"asaba_tmin_monthly_timeseries.png"`.
-  📌 **Skill gained**: Turning raw gridded data into **station-like time series** for interpretation.

---

## ⚠️ **Challenges Faced & How You Solved Them**

1. **Issue: CFTime vs datetime64**

   -  NetCDF time was stored as `CFTimeIndex` (not compatible with matplotlib).
   -  ❌ First attempts failed when trying to plot.
   -  ✅ Solution: Used `asaba.indexes['time'].to_datetimeindex()` to convert time to native datetime64.

2. **Issue: Location Selection**

   -  Wanted data for Abuja/Asaba but dataset is **gridded** (not exact coordinates).
   -  ❌ Direct indexing failed.
   -  ✅ Solution: Used `sel(lat=..., lon=..., method='nearest')` to pick the closest grid point.

3. **Issue: Visualization**

   -  Initial plots were messy on the x-axis.
   -  ✅ Solution: Applied `mdates.MonthLocator()` and `DateFormatter('%b %Y')` for clean monthly ticks.

---

## 📌 **Where You Are Now**

You’ve successfully completed:

-  ✅ Week 1: Setup & Dataset Familiarization
-  ✅ Week 2, Day 1: Extract and plot a daily Tmin time series (Asaba, 2025)

📍 **Your exact position in roadmap:**
👉 **Week 2, Day 2 — Monthly Trend Analysis**

---

## 🎯 **Where You’re Going Next**

### **Immediate Next Step (Week 2, Day 2)**

-  Aggregate daily Tmin into **monthly averages** (`groupby('time.month')`).
-  Plot a **monthly mean Tmin trend** for Asaba.
-  Interpret: which months are coldest/warmest?

### **After That (Week 2, Day 3–4)**

-  Expand analysis from **point time series** → **spatial maps**:

   -  Map Tmin for Nigeria on a chosen day.
   -  Overlay with Cartopy boundaries.
   -  Animate daily maps across a month (time-lapse).

### **End of Week 2 Deliverable**

-  A **climate notebook** with:

   -  Time series for a city
   -  Monthly mean trend
   -  A simple spatial map

-  📌 This will demonstrate ability to **explore climate datasets in both time & space**.

---

## 🔮 **Bigger Picture (Weeks 3 & 4)**

-  **Week 3**: Move into AI/ML

   -  Random Forests for next-day Tmin prediction
   -  CNNs for cloud/fog detection
   -  LSTMs for rainfall nowcasting

-  **Week 4**: Final Project

   -  Build a **dashboard / AI prototype**
   -  Write an **academic report** for NIMET supervisors
   -  Prepare to defend your methodology

---

# 📝 **Summary in Plain Words**

You’ve set up your coding environment, loaded a real NOAA dataset, and successfully plotted a **year-long Tmin series for Asaba**. Along the way, you tackled tricky issues with **time decoding**, **grid selection**, and **plot formatting** — and you solved them like a scientist would.

Right now, you’re standing at the door of **Week 2, Day 2**: learning how to **compress daily data into monthly climate summaries**, which is exactly how real climatologists detect **seasonal cycles** and compare across years.

---

👉 Question for you, Jadon:
Would you like me to now **start unfolding the meteorological theory of monthly averages** (why we compute them, what they show), before we touch any code?

