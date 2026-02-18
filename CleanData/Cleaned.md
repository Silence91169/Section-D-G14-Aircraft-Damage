# Wildlife Strike Data Cleaning & Preprocessing

## Project Context

This dataset contains recorded wildlife strike incidents involving aircraft operations.  
To ensure analytical reliability and KPI accuracy, structured data cleaning, normalization, and feature engineering were performed prior to pivot analysis and dashboard development.

All preprocessing activities were conducted exclusively in Google Sheets in accordance with capstone project guidelines.

---

# 1. Data Quality Issues Identified

Initial inspection of the raw dataset revealed:

- Inconsistent capitalization across categorical fields  
- Missing categorical values affecting grouping  
- Missing numerical values affecting aggregation  
- Mixed binary encodings (Y/N, 1/0, blanks)  
- Inconsistent species and location formatting  

These inconsistencies could distort KPI calculations and fragment pivot analysis if left unaddressed.

---

# 2. Cleaning Strategy & Standardization

## 2.1 Text Standardization

Issue: Mixed capitalization caused duplicate category groupings.

Logic Used:
=PROPER(cell)

Applied To:
- Operator  
- Airport  
- Species Name  

This ensured consistent pivot grouping and eliminated redundant category splits.

---

## 2.2 Handling Missing Categorical Values

Issue: Blank categorical entries fragmented pivot tables and dashboards.

Logic Used:
=IF(ISBLANK(cell),"STANDARD_VALUE",cell)

Standardized Values Applied:

- Engine Type → NA  
- State → UNKNOWN  
- FAA Region → NA  
- Flight Phase → UNKNOWN  
- Visibility → UNKNOWN  
- Precipitation → NONE  
- Flight Impact → NONE  

This preserved all incident records while ensuring analytical grouping integrity.

---

## 2.3 Handling Missing Numerical Values

Issue: Blank numeric fields disrupted aggregations and KPI calculations.

Logic Used:
=IF(ISBLANK(cell),0,cell)

Applied To:
- Engines  
- Height  
- Speed  
- Species Quantity  

Important Clarification:

Blank numerical values were standardized to 0 strictly for aggregation consistency.  
This does not imply that missing values represent true zero measurements.  
Some blanks may reflect unreported data rather than operational ground-level conditions.

---

## 2.4 Binary Field Normalization

Issue: Binary indicators were inconsistently encoded (Y/N, 1/0, blanks).

Y/N Conversion:
=IFS(cell="Y","Yes",cell="N","No",cell="","Unknown")

1/0 Conversion:
=IF(cell=1,"Yes","No")

Applied To:
- Warning Issued  
- Aircraft Damage  
- Engine Ingested  

All binary variables were standardized to Yes / No / Unknown format for accurate KPI computation.

---

# 3. Feature Engineering

Derived categorical variables were created to enhance analytical segmentation and risk assessment.

## 3.1 Height Band (Operational Risk Segmentation)

Purpose: Categorize altitude into operational exposure zones.

=IF(height=0,"On Ground",
   IF(height<=500,"Low Altitude",
      IF(height<=2000,"Medium Altitude","High Altitude")))

These thresholds reflect aviation operational bands during taxi, takeoff, climb, and cruise phases.

---

## 3.2 Speed Band (Strike Severity Segmentation)

Purpose: Classify aircraft speed into severity-related bands.

=IF(speed=0,"Stationary",
   IF(speed<=100,"Low Speed",
      IF(speed<=200,"Medium Speed","High Speed")))

This enables correlation analysis between aircraft velocity and damage probability.

---

# 4. Data Validation & Integrity Checks

To ensure cleaning logic did not distort the dataset:

- Verified total incident count remained unchanged  
- Cross-checked pivot totals against raw dataset totals  
- Recalculated binary Yes/No distributions post-normalization  
- Confirmed no row deletions during preprocessing  
- Ensured engineered bands preserved original numerical distributions  

These steps ensured structural integrity and audit consistency.

---

# 5. Assumptions

The following assumptions were applied:

- Missing categorical values represent unreported data, not absence of occurrence  
- Zero values in altitude or speed represent reported measurements, not imputed corrections  
- Binary strike indicators accurately reflect reported outcomes  
- Height and speed thresholds align with aviation operational exposure ranges  
- Reporting standards are assumed reasonably consistent across included years  

---

# 6. Impact on KPI Accuracy

The cleaning and normalization process directly improved reliability of:

- Engine Ingestion Rate (%)  
- Damage Probability by Flight Phase  
- Seasonal Migration Risk Analysis  
- Engine Type Vulnerability Index  
- Weather-Based Damage Risk (%)  

Without preprocessing:

- Damage rates could be under- or overestimated  
- Blank values would fragment pivot categories  
- Binary metrics would be misclassified  
- Dashboard filters would produce inconsistent outputs  

---

# 7. Limitations

- Missing values may reflect under-reporting rather than true zero values  
- Engine Type codes were used as provided; no external technical mapping was applied  
- Seasonal analysis assumes consistent reporting practices across years  
- No financial cost variables were available for impact modeling  
- Correlation findings do not imply statistical causation  

---

# Final Outcome

Following preprocessing, the dataset is now:

- Structurally consistent  
- Fully standardized  
- Audit-ready  
- KPI-compliant  
- Dashboard-compatible  
- Suitable for analytical reporting and operational recommendation modeling  
