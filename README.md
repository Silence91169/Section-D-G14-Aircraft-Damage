# ✈️ Wildlife Strike Risk Analytics Dashboard

An analytical dashboard project focused on identifying high-risk operational, environmental, and biological conditions associated with aircraft wildlife strikes.

---

## 📌 Project Overview

Wildlife strikes are a recurring aviation safety challenge. While many strikes cause minimal impact, a subset leads to aircraft damage, engine ingestion, operational disruption, and maintenance costs.

This project transforms historical FAA wildlife strike data into actionable safety insights using structured data cleaning, KPI development, exploratory analysis, and an interactive dashboard.

---

## 🎯 Objectives

- Identify high-risk flight phases associated with aircraft damage  
- Analyze seasonal wildlife strike patterns  
- Measure engine ingestion severity impact  
- Evaluate environmental risk factors  
- Support data-driven aviation safety decisions  

---

## 🛠 Tools Used

- **Google Sheets** (Data cleaning, pivot tables, KPI development)
- **Dashboard Visualization in Sheets**
- **GitHub** (Version control & documentation)

No external programming tools were used to comply with capstone guidelines.

---

## 📊 Dashboard Preview

### Top KPI Section

- Engine Ingestion Rate
- High-Risk Flight Phase (Probability-Based)
- Migration Season Peak
- Engine Type Vulnerability Index

---

### Monthly Strike Trend

![Monthly Trend](Documentation/Images/img4.png)

---

### Aircraft Damage by Flight Phase

![Flight Phase Damage](Documentation/Images/img5.png)

---

### Annual Incident Trend

![Annual Trend](Documentation/Images/img6.png)

---

## 🔍 Key Insights

- **EN ROUTE phase shows highest damage probability (20.38%)**
- Approach and Climb account for highest total damage incidents
- September is the peak wildlife migration month
- Engine ingestion significantly increases damage severity
- Snow conditions amplify aircraft damage risk
- Multi-animal strikes increase probability of severe outcomes
- Certain FAA regions and airports show concentrated exposure

---

## 📈 KPI Framework

| KPI | Definition | Purpose |
|------|------------|----------|
| Damage Rate | Damage ÷ Total Incidents | Measures strike severity |
| Engine Ingestion Rate | Ingestion ÷ Total Incidents | Identifies high-severity events |
| Seasonal Risk Index | Monthly ÷ Annual Average | Detects peak months |
| Phase Risk Index | Damage by Phase ÷ Total Damage | Identifies operational vulnerability |

---

## 📂 Repository Structure

├── CleanData/
├── RawData/
├── Pivot/
├── Dashboard/
├── Documentation/
│ ├── Wildlife_Strike_Risk_Analysis_Report.md
│ └── Images/
│ ├── img1.png
│ ├── img2.png
│ ├── img3.png
│ ├── img4.png
│ ├── img5.png
│ └── img6.png
├── Presentation/
└── README.md


---

## 📌 Dataset Information

- **Source:** Kaggle – Aircraft Wildlife Strikes (1990–2015)
- **Original Provider:** FAA Wildlife Strike Database
- **Records:** 9,999
- **Variables:** 24

Each record represents one wildlife strike incident involving civil aircraft.

---

## 🧹 Data Cleaning Highlights

- Standardized categorical values (YES / NO / UNKNOWN)
- Replaced missing categorical values with "UNKNOWN"
- Treated blank numerical values as 0
- Created Height Bands & Speed Bands
- No outliers removed (retained for safety analysis integrity)

All transformations performed in Google Sheets.

---

## 🚨 Recommendations

- Enhance wildlife monitoring during approach & takeoff
- Implement seasonal risk alerts (Aug–Oct)
- Strengthen engine inspection after ingestion events
- Deploy targeted bird control at hotspot airports
- Introduce snow-weather advisories
- Use dashboard for proactive risk monitoring

---


## 👥 Team Members

| Name | 
|------|
| Shitanshu |
| Yaseen |
| Praveen |
| Tanisha |
| Yogesh |
| Anish |

**Institute:** Newton School of Technology  
**Faculty:** Archit Raj  

---

## 📜 License

This project is created for academic and analytical purposes under capstone guidelines.

---

## ⭐ Final Outcome

The project successfully converts wildlife strike data into a structured risk intelligence framework that supports proactive aviation safety decision-making.


