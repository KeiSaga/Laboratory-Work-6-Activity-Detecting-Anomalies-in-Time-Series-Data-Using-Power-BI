# 📊 IS107 — Laboratory Work 6
## Detecting Anomalies in Time-Series Data Using Power BI
https://drive.google.com/drive/folders/1tgTpODeO_7Bh4mvYUtPCVX1MJfAEXFnc?usp=drive_link
![Power BI](https://img.shields.io/badge/Tool-Power%20BI%20Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Complete-22C55E?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Dataset-tourism--details.csv-38BDF8?style=for-the-badge)

---

## 📋 Table of Contents

1. [Overview](#-overview)
2. [Objectives](#-objectives)
3. [Materials Required](#-materials-required)
4. [Dataset Description](#-dataset-description)
5. [Step-by-Step Procedure](#-step-by-step-procedure)
   - [Part 1: Data Preparation](#part-1-data-preparation)
   - [Part 2: Data Visualization](#part-2-data-visualization)
   - [Part 3: Enable Anomaly Detection](#part-3-enable-anomaly-detection)
   - [Part 4: Explain Anomalies](#part-4-explain-anomalies)
   - [Part 5: Interpretation & Analysis](#part-5-interpretation--analysis)
   - [Part 6: Enhancement Task](#part-6-enhancement-task)
6. [Expected Output](#-expected-output)
7. [Analysis Summary](#-analysis-summary)
8. [Key Findings](#-key-findings)
9. [Additional Anomaly Dataset](#-additional-anomaly-dataset)
10. [References](#-references)

---

## 🔍 Overview

This laboratory work explores **AI-powered anomaly detection** in Microsoft Power BI using real tourism data from the Netherlands (2012–2021). Microsoft's Power BI uses deep learning (DL) methods to automatically identify statistically unusual data points in time-series data — no manual labeling required.

The activity is based on **Chapter 5: Detecting Anomalies in Your Data** from *Artificial Intelligence with Power BI* (Packt Publishing).

---

## 🎯 Objectives

By the end of this activity, students should be able to:

| # | Objective |
|---|-----------|
| 1 | Import and prepare time-series data in Power BI |
| 2 | Create a line chart for trend visualization |
| 3 | Enable and interpret anomaly detection |
| 4 | Analyze possible causes of anomalies using explanatory variables |
| 5 | Evaluate the reliability of AI-generated insights |

---

## 🛠️ Materials Required

- **Power BI Desktop** — [Download free from Microsoft](https://powerbi.microsoft.com/desktop/)
- **Chapter 5 Reference PDF** — *Detecting Anomalies in Your Data Using Power BI*
- **Primary Dataset** — `tourism-details.csv` (920 rows)
- **Additional Dataset** — 20 supplemental anomaly rows (see [Part 6](#part-6-enhancement-task))

> ⚙️ **Note:** Ensure the **Auto date/time** option is enabled in Power BI before starting.  
> Go to: **File → Options → Current File → Data Load → Auto date/time**

---

## 📁 Dataset Description

**File:** `tourism-details.csv`  
**Source:** [GitHub – PacktPublishing/Artificial-Intelligence-with-Power-BI](https://raw.githubusercontent.com/PacktPublishing/Artificial-Intelligence-with-Power-BI/main/Chapter05/tourismdetails.csv)  
**Period Covered:** January 2012 – July 2021  
**Total Rows:** ~920

| Column | Data Type | Description |
|--------|-----------|-------------|
| `Period` | Date | Monthly date (e.g., `1-Jan-12`) |
| `Accommodation Type` | Text | Hotel · Holiday Park · Camping · Group Accommodations |
| `Travel` | Text | `Domestic` or `International` |
| `Tourists` | Whole Number | Monthly visitor count (e.g., `735,000`) |

---

## 📐 Step-by-Step Procedure

### Part 1: Data Preparation

**Steps 1–3**

1. **Download** `tourism-details.csv` and save it to your local system.
2. Open **Power BI Desktop**.
3. Click **Home → Get Data → Text/CSV**.
4. Navigate to the saved file, click **Open**, then click **Load**.
5. In **Power Query Editor**, verify the following column types:

   | Column | Correct Type |
   |--------|-------------|
   | Period | Date |
   | Accommodation Type | Text |
   | Travel | Text |
   | Tourists | Whole Number |

6. Click **Close & Apply** to load the data.

---

### Part 2: Data Visualization

**Steps 4–6**

1. In the **Visualizations** pane, click the **Line Chart** icon.
2. Map fields:
   - Drag `Period` → **Axis**
   - Drag `Tourists` → **Values**
3. At the top of the visual, click the **"Expand all down one level in the hierarchy"** button (⬇⬇) to drill down to monthly granularity.

> 📸 **Screenshot checkpoint:** Save a screenshot of your monthly line chart before enabling anomaly detection.

---

### Part 3: Enable Anomaly Detection

**Steps 7–9**

There are **two methods** to enable anomaly detection:

**Method A — Top Ribbon:**
1. Select the line chart visual.
2. Click the **Data/Drill** tab in the top ribbon.
3. Click **Find Anomalies**.

**Method B — Analytics Pane (Recommended):**
1. In the **Visualizations** pane, click the **Analytics** tab (magnifying glass icon).
2. Expand **Find Anomalies**.
3. Click **+ Add**.

**What to observe after enabling:**
- A **shaded gray band** appears around the trend line (expected value range / confidence interval).
- **Anomaly markers** (icons) appear on data points outside this range.
- **Four anomalies** should be visible: April 2019, June 2019, April 2020, May 2020.

> 📸 **Screenshot checkpoint:** Save a screenshot of the line chart showing the anomaly markers and shaded band.

---

### Part 4: Explain Anomalies

**Steps 10–12**

1. In **Visualizations → Analytics → Find Anomalies**, locate the **Explain by** box.
2. Drag the following fields into **Explain by**:
   - `Accommodation Type`
   - `Travel`
3. Click **Apply**.
4. **Click on an anomaly marker** on the line chart (e.g., April 2019).
5. The **Anomalies pane** opens on the left.

**Analyzing the Anomalies Pane:**
- **Summary** — States whether the value was unexpectedly high or low.
- **Possible explanations** — Lists contributing factors with a **Strength** score.
- **Comparison charts** — Visualizes the explaining variable next to the total.

> 📸 **Screenshot checkpoint:** Save a screenshot of the Anomalies pane for both the 2019 and 2020 anomalies.

---

### Part 5: Interpretation & Analysis

**Step 13 — Answer the following guide questions:**

| Guide Question | Key Points to Address |
|---|---|
| What trend and seasonality patterns are observed? | Upward trend 2012–2019; seasonal peaks in summer, troughs in winter |
| Which anomalies are obvious vs. subtle? | 2020 = obvious (visible dip); 2019 = subtle (detected by AI only) |
| What factors contributed to anomalies? | 2019: Holiday Park surge; 2020: International travel collapse |
| Are the explanations logically valid? | 2020 = valid (COVID-19); 2019 = plausible but needs domain verification |

Write your analysis in **5–8 sentences** (see [Analysis Summary](#-analysis-summary) below for reference).

---

### Part 6: Enhancement Task

**Steps 14–16**

1. Open `tourism-details.csv` in a text editor or Excel.
2. **Append the 20 additional rows** at the bottom of the file (see [Additional Anomaly Dataset](#-additional-anomaly-dataset)).
3. Save the file.
4. In Power BI, click **Home → Refresh**.
5. Observe:
   - Newly detected anomalies for 2021–2022.
   - Changes in the confidence band.
   - How extremely low values (100, 150, 200 tourists) are flagged.

---

## 📤 Expected Output

| Output | Description |
|--------|-------------|
| ✅ Line Chart Screenshot | Shows the line chart with anomaly markers and shaded confidence band |
| ✅ Anomalies Pane Screenshot | Shows the Anomalies pane with possible explanation (e.g., April 2019 – Holiday Park) |
| ✅ Short Analysis | 5–8 sentences interpreting the detected anomalies |

---

## 📝 Analysis Summary

*(5–8 sentences — to be written based on your own Power BI observations)*

The tourism dataset exhibits a clear **upward trend from 2012 to 2019** with consistent seasonal patterns — visitor numbers peak during summer months (July–August) and dip during winter (January–February). Power BI's anomaly detection algorithm identified **four anomalies** across the dataset. The anomalies in **April and June 2019** were unexpected and subtle — not visible through simple visual inspection; the model flagged these because tourist counts exceeded the predicted confidence range, with a possible explanation pointing to increased Holiday Park occupancy. In contrast, the anomalies in **April and May 2020** were visually obvious, corresponding to the COVID-19 pandemic, which caused a dramatic collapse in international tourism. Power BI's "Explain by" feature correctly identified that the 2020 anomaly was driven primarily by the **collapse in international travel**, while domestic travel recovered more quickly. The 2019 Holiday Park explanation is plausible — perhaps driven by promotional campaigns or shifting travel preferences — but would require domain expert validation to confirm. This activity demonstrates that AI-assisted anomaly detection can uncover both **obvious and subtle data irregularities**, making it a powerful tool for business intelligence and data quality monitoring. However, human judgment and domain knowledge remain essential for correctly interpreting and acting on AI-generated insights.

---

## 🔑 Key Findings

| Anomaly | Period | Direction | Possible Cause | Type |
|---------|--------|-----------|----------------|------|
| 1 | April 2019 | 🔺 Unexpectedly High | Surge in Holiday Park accommodation | Subtle |
| 2 | June 2019 | 🔺 Unexpectedly High | Holiday Park / seasonal factors | Subtle |
| 3 | April 2020 | 🔻 Unexpectedly Low | COVID-19 pandemic (all travel) | Obvious |
| 4 | May 2020 | 🔻 Unexpectedly Low | COVID-19 (International travel collapse) | Obvious |

---

## 📦 Additional Anomaly Dataset

Append the following 20 rows to `tourism-details.csv` for the **Part 6 Enhancement Task**:

```csv
Period,Accommodation Type,Travel,Tourists
2021-01-01,Hotel,Domestic,5000
2021-02-01,Hotel,International,200
2021-03-01,Holiday Park,Domestic,9500
2021-04-01,Camping,Domestic,12000
2021-05-01,Hotel,International,150
2021-06-01,Holiday Park,International,300
2021-07-01,Camping,Domestic,18000
2021-08-01,Hotel,Domestic,20000
2021-09-01,Holiday Park,Domestic,4000
2021-10-01,Camping,International,250
2021-11-01,Hotel,Domestic,3500
2021-12-01,Holiday Park,Domestic,22000
2022-01-01,Camping,Domestic,3000
2022-02-01,Hotel,International,100
2022-03-01,Holiday Park,Domestic,14000
2022-04-01,Camping,Domestic,16000
2022-05-01,Hotel,Domestic,25000
2022-06-01,Holiday Park,International,500
2022-07-01,Camping,Domestic,21000
2022-08-01,Hotel,International,300
```

> ⚠️ Values like `100`, `150`, `200`, and `300` tourists are drastically lower than the historical baseline (~700,000–5,000,000) and will trigger new anomaly detections when the report is refreshed.

---

## 📚 References

- Decamps, J. (2022). *Artificial Intelligence with Power BI*. Packt Publishing.  
  — Chapter 5: Detecting Anomalies in Your Data Using Power BI (pp. 119–126)
- Microsoft Docs. (2023). [Anomaly detection in Power BI visuals](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-anomaly-detection)
- Dataset Source: [PacktPublishing/Artificial-Intelligence-with-Power-BI on GitHub](https://github.com/PacktPublishing/Artificial-Intelligence-with-Power-BI)

---

<div align="center">

**IS107 — Artificial Intelligence Tools and Applications**  
Laboratory Work 6 · Caraga State University

</div>
