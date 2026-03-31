# FUTURE_DS_03
Power BI dashboard analyzing bank marketing campaign data — customer acquisition, conversion trends and financial risk analysis

# 📊 Bank Marketing Campaign Dashboard
### Built with Microsoft Power BI

---

## 📌 Project Overview
This project analyzes a **Bank Marketing Dataset** to uncover insights about customer acquisition, campaign performance, and financial risk. The dashboard was built as part of an internship task to demonstrate end-to-end data analysis and visualization skills using Power BI.

---

## 📂 Dataset
- **Source:** UCI Machine Learning Repository — Bank Marketing Dataset
- **File:** `bank.csv`
- **Rows:** 45,211 customer records
- **Columns:** 17 attributes including age, job, balance, education, contact, campaign, and more

---

## 📊 Dashboard Features

### KPI Cards
- Total Leads
- Total Customers
- Conversion Rate %
- Drop-offs
- Average Balance
- Default Rate %

### Visuals Included
| Visual | Columns Used | Insight |
|--------|-------------|---------|
| Funnel Chart | Funnel Stage | Lead to Customer conversion flow |
| Stacked Bar Chart | Job, Housing, Loan | Housing & loan status by job type |
| Donut Chart | Education | Customer education level distribution |
| Treemap | Job | Customer count by job segment |
| Line Chart | Date, Conversion Rate | Monthly conversion rate trend |
| Scatter Chart | Campaign, Conversion Rate | Campaign count vs conversion rate |
| Clustered Bar Chart | Education, Balance | Average balance by education level |
| Age Group Bar Chart | Age | Customer age group distribution |

---

## 🔍 Key Insights
- **Longer call durations** strongly correlate with higher conversion rates
- **Retired and management** job segments have the highest number of customers
- **Tertiary educated** customers hold significantly higher average balances
- **Cellular contact** method yields better conversion than telephone
- Customers with both **loan and default = yes** represent the highest risk segment

---

## 🛠️ Tools Used
- **Microsoft Power BI Desktop**
- **DAX** (Data Analysis Expressions) for custom measures
- **Power BI AppSource** — Box and Whisker chart visual

---

## 📐 DAX Measures Created
```
Default Rate % = 
DIVIDE(
    COUNTROWS(FILTER('bank-full', 'bank-full'[default] = "yes")),
    COUNTROWS('bank-full')
) * 100
```

```
Conversion by Day = 
DIVIDE(
    CALCULATE(COUNTROWS('bank-full'), 'bank-full'[Funnel Stage] = "Customer"),
    COUNTROWS('bank-full')
) * 100
```

```
High Risk Flag = 
IF(
    'bank-full'[default] = "yes" && 
    'bank-full'[loan] = "yes" && 
    'bank-full'[balance] < 0,
    "High Risk", "Normal"
)
```

---

## 📁 Repository Structure
```
bank-marketing-dashboard/
│
├── Bank_Marketing_Dashboard.pbix    # Power BI dashboard file
├── bank-full.csv                    # Original dataset
├── dashboard_screenshot.png         # Dashboard preview image
├── README.md                        # Project documentation
```

---

## 🚀 How to Open
1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/downloads/) (free)
2. Clone this repository or download the files
3. Open `Bank_Marketing_Dashboard.pbix` in Power BI Desktop
4. Explore the dashboard using the slicers and filters

---

## 👤 Author
- **Name:** ZAHRA JEELANI
- **Internship:** FUTURE INTERNS DATA ANALYTICS INTERNSHIP
- **Date:** March 2026

---

## 📜 License
This project uses publicly available data from the UCI Machine Learning Repository for educational purposes.
