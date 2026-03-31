# FUTURE_DS_03
Power BI dashboard analyzing bank marketing campaign data — customer acquisition, conversion trends and financial risk analysis
📊 Bank Marketing Campaign Dashboard
Built with Microsoft Power BI

📌 Project Overview
This project analyzes a Bank Marketing Dataset to uncover insights about customer acquisition, campaign performance, and financial risk. The dashboard was built as part of an internship task to demonstrate end-to-end data analysis and visualization skills using Power BI.

📂 Dataset

Source: UCI Machine Learning Repository — Bank Marketing Dataset
File: bank-full.csv
Rows: 45,211 customer records
Columns: 17 attributes including age, job, balance, education, contact, campaign, and more


📊 Dashboard Features
KPI Cards

Total Leads
Total Customers
Conversion Rate %
Drop-offs
Average Balance
Default Rate %

Visuals Included
VisualColumns UsedInsightFunnel ChartFunnel StageLead to Customer conversion flowStacked Bar ChartJob, Housing, LoanHousing & loan status by job typeDonut ChartEducationCustomer education level distributionTreemapJobCustomer count by job segmentLine ChartDate, Conversion RateMonthly conversion rate trendScatter ChartCampaign, Conversion RateCampaign count vs conversion rateScatter ChartDuration, Conversion RateCall duration vs conversion rateClustered Bar ChartEducation, BalanceAverage balance by education levelAge Group Bar ChartAgeCustomer age group distributionMatrix VisualLoan, DefaultFinancial risk matrix

🔍 Key Insights

Longer call durations strongly correlate with higher conversion rates
Retired and management job segments have the highest number of customers
Tertiary educated customers hold significantly higher average balances
Cellular contact method yields better conversion than telephone
Customers with both loan and default = yes represent the highest risk segment


🛠️ Tools Used

Microsoft Power BI Desktop
DAX (Data Analysis Expressions) for custom measures
Power BI AppSource — Box and Whisker chart visual


📐 DAX Measures Created
Default Rate % = 
DIVIDE(
    COUNTROWS(FILTER('bank-full', 'bank-full'[default] = "yes")),
    COUNTROWS('bank-full')
) * 100
Conversion by Day = 
DIVIDE(
    CALCULATE(COUNTROWS('bank-full'), 'bank-full'[Funnel Stage] = "Customer"),
    COUNTROWS('bank-full')
) * 100
High Risk Flag = 
IF(
    'bank-full'[default] = "yes" && 
    'bank-full'[loan] = "yes" && 
    'bank-full'[balance] < 0,
    "High Risk", "Normal"
)

📁 Repository Structure
bank-marketing-dashboard/
│
├── Bank_Marketing_Dashboard.pbix    # Power BI dashboard file
├── bank-full.csv                    # Original dataset
├── dashboard_screenshot.png         # Dashboard preview image
├── README.md                        # Project documentation
