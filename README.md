# 💳 BNPL Credit Risk & Portfolio Analysis (PayLaterCo)

## 📌 Project Overview
This project investigates a severe 40% surge in delinquency rates during Q1 2026 for "PayLaterCo", a Buy Now, Pay Later (BNPL) provider. By analyzing a portfolio of over 267,000 loans, this analysis aims to debunk operational assumptions (seasonality), uncover structural vulnerabilities in the underwriting process, and pinpoint the root cause of the credit degradation to propose targeted risk mitigation strategies.

> **View the full 4-page interactive dashboard [here](insert_your_powerbi_public_link_here) or download the PDF report [here](insert_pdf_github_link).**

## 🛠️ Tech Stack & Data Engineering
* **Data Processing & Analysis (SQL/PostgreSQL):** Engineered advanced queries (multi-level CTEs, aggregations, and Joins) to integrate 5 distinct datasets (Loans, Merchants, Customers, Applications, Repayments). Restructured the definition of "Bad Loans" by discovering and including the hidden 'restructured' status to ensure absolute data integrity.
* **Visualization (Power BI):** Designed a 4-page executive dashboard featuring dynamic risk-volume scatter matrices, dual-axis trend comparisons, and categorical drill-downs for seamless data storytelling.
* **Metric Calculation (DAX):** Developed custom measures to track localized Delinquency Rates, Approval Rates across merchant cohorts, and Total Loan Volumes.

---

## 💡 Key Insights & Discoveries

### 1. The Seasonality Myth Debunked
Operations initially attributed the rising bad debt to cyclical Q1 softness. However, cohort analysis proved this was a structural break: the delinquency rate spiked to ~10.8% in Q1 2026, drastically deviating from the historical Q1 baseline of ~7%.

### 2. Simpson’s Paradox (The Mix Shift)
By segmenting the portfolio, a textbook Simpson’s Paradox emerged. Legacy merchants (onboarded prior to Q4 2025) maintained a highly stable delinquency rate of ~7%. The entire 40% macroeconomic surge was driven exclusively by a newly onboarded merchant cohort, which suffered an unprecedented ~19% default rate.

**

### 3. Underwriting Vulnerability (The Funnel Leak)
Application funnel analysis revealed a fatal flaw in the credit scoring logic. The highly toxic "New Merchant" cohort was approved at a significantly looser rate (80.97%) compared to the historically safe legacy cohort (72.96%). The system was actively enabling riskier acquisitions to prioritize short-term growth.

### 4. Severe Risk Concentration (The Root Cause)
A deep-dive matrix (Category × KYC Tier × Term) isolated the core threat. Risk was not spread evenly across the new merchants; it was heavily concentrated in the **Electronics** category. 

The most severe operational leak was found in **3-month loans for Basic KYC users**, hitting a critical **28.96% default rate** across a massive volume of 1,478 loans. (Additionally, Premium users on 12-month terms also hit a 35.1% default, though at a lower volume). This concentrated pattern strongly indicates targeted exploitation of high-value, highly liquid goods under relaxed underwriting conditions, rather than standard, widespread credit deterioration.

**
## 📊 Dashboard Previews
![Dashboard]([https://github.com/ThanhDustin/project-Storm-Events-Data-Analysis-Visualization/blob/main/hinhoverview.png](https://github.com/ThanhDustin/project-BNPL-Credit-Risk-Fraud-Analysis-/blob/main/trang1.png))
![Dashboard]([https://github.com/ThanhDustin/project-Storm-Events-Data-Analysis-Visualization/blob/main/hinhoverview.png](https://github.com/ThanhDustin/project-BNPL-Credit-Risk-Fraud-Analysis-/blob/main/trang2.png))
![Dashboard]([https://github.com/ThanhDustin/project-Storm-Events-Data-Analysis-Visualization/blob/main/hinhoverview.png](https://github.com/ThanhDustin/project-BNPL-Credit-Risk-Fraud-Analysis-/blob/main/trang3.png))
![Dashboard]([https://github.com/ThanhDustin/project-Storm-Events-Data-Analysis-Visualization/blob/main/hinhoverview.png](https://github.com/ThanhDustin/project-BNPL-Credit-Risk-Fraud-Analysis-/blob/main/trang4.png))

---

## 🚀 Recommendations
1. **Surgical Credit Freeze:** Immediately halt or heavily restrict Electronics financing for the "New Merchant" cohort, particularly for Basic KYC applicants.
2. **Underwriting Recalibration:** Align the approval threshold for new merchants (currently ~81%) back to the legacy baseline (~73%) until enhanced credit scoring models are deployed.
3. **Enhanced KYC Workflow:** Mandate Premium KYC verification for all Electronics purchases exceeding standard volume thresholds.
