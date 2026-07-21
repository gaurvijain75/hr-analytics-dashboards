# HR Analytics: Data Preprocessing & Dashboard Insights

Cleaning, transforming, and modeling an HR employee-attrition dataset using Power Query, then deriving key workforce insights through an interactive Power BI dashboard.

## 📊 Overview

This project analyzes an HR employee dataset to understand workforce composition and the drivers behind employee attrition — turning a messy raw export into a clean, dashboard-ready dataset and surfacing actionable retention insights.

## 📁 Dataset

- **Size:** 1,482 employee records → 37 original columns (reduced to 34 after cleaning)
- **Source:** Excel/CSV, loaded via Power Query
- **Target variable:** `Attrition` (Yes/No)

**Key field groups:**
- **Identity & Demographics:** EmpID, Age, AgeGroup, Gender, Education, EducationField
- **Job & Department:** Department, JobRole, BusinessTravel, DistanceFromHome, YearsAtCompany
- **Compensation:** DailyRate, HourlyRate, SalarySlab, SalaryHike %, StockOptionLevel
- **Satisfaction & Tenure:** JobSatisfaction, EnvironmentSatisfaction, WorkLifeBalance, TotalExperience

## 🧹 Data Preprocessing Pipeline (Power Query)

1. **Corrected data types** — set EmpID as text, numeric tenure fields as Whole Number/Int64
2. **Sorted & removed invalid top rows** — stripped 61 blank/misaligned rows
3. **Detected duplicate records** — grouped by EmpID, found 16 duplicate IDs
4. **Removed duplicate records** — kept first occurrence via `Table.Distinct`
5. **Standardized inconsistent text** — merged "Travel_Rarely" / "TravelRarely" into one value
6. **Renamed unclear columns** — e.g. "DistanceFromHome(KM)" → "Distance From Home"
7. **Removed redundant/constant columns** — dropped EmployeeCount, Over18, StandardWorkingHours (37 → 34 columns)
8. **Trimmed & cleaned text fields** — applied `Text.Trim` and `Text.Clean`
9. **Added a conditional column** — created an Attrition Count column for visualization

## 📈 Dashboard Highlights

| Metric | Value |
|---|---|
| Total Employees | 1,417 |
| Active Employees | 1,186 |
| Attrition Count | 231 (~16.3%) |
| Average Age | 36.9 yrs |
| Average Experience | 11.3 yrs |

## 🔍 Key Findings

- **Department risk:** Administration (36%) and Sales (23%) drive the largest share of attrition, despite Operations having the largest headcount (512 employees)
- **Gender gap:** Attrition skews heavily male (63.2%) vs. female (36.8%)
- **Tenure & experience:** Attrition is concentrated among employees with 0–5 years of experience
- **Salary slab:** The 6–10 LPA band records the highest attrition volume (73 exits) vs. the 10+ LPA band (48 exits)
- **Job roles:** Sales Executive and Laboratory Technician show the highest attrition counts

## ✅ Recommendations

1. Prioritize retention programs for early-career employees (0–5 years)
2. Review workload, growth paths, and pay structure in Administration and Sales
3. Investigate the gender attrition gap through exit interviews and engagement surveys
4. Re-evaluate compensation bands, especially the 6–10 LPA slab, against market benchmarks

## 🛠️ Tools Used

- **Power Query (M language)** — data cleaning and transformation
- **Power BI** — dashboard and visualization

## 📂 Files

- `HR_Analytics_Preprocessing_Dashboard.pptx` — full presentation walking through the preprocessing steps and dashboard

---
*Project by Gaurvi Jain | BDT Lab Assignment 1 | LY B.Tech CSE (AI & DS)*
