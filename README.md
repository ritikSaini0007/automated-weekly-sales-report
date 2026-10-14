# 📈 Automated Weekly Sales Report

An n8n automation workflow that collects sales data from Google Sheets, analyzes weekly performance, and emails an AI-generated sales report to the founder every Monday at 9 AM.

Built as part of a **Data Analytics & Finance Automation Portfolio**.

## 🎯 What It Does

Every Monday morning, this workflow automatically:

- Reads sales data from Google Sheets.
- Analyzes the last 7 days of sales performance.
- Calculates revenue, orders, units sold, and top-performing products, customers, sales representatives, and regions.
- Tracks payment status.
- Compares the current week with the previous week using week-over-week percentage changes.
- Generates a professional sales report using OpenAI GPT-4o-mini.
- Converts the report into formatted HTML and sends it through Gmail.
- Sends a no-data notification if no sales records are available.
- Uses a separate error workflow to send alerts when the automation fails.

## ⚙️ Workflow Architecture

```text
Schedule Trigger (Every Monday, 9 AM)
                 |
                 ▼
       Read Sales Data
        (Google Sheets)
                 |
                 ▼
      Analyze & Build Report
           (JavaScript)
                 |
                 ▼
            Has Data?
            /       \
          Yes        No
           |          |
           ▼          ▼
    Generate AI    No-Data Email
       Report
           |
           ▼
     Markdown to HTML
           |
           ▼
      Send Email
        (Gmail)

 Separate Error Workflow
           |
           ▼
       Error Alert
```

## ✨ Key Features

- **Weekly Performance Analysis:** Automatically calculates important sales KPIs.
- **Week-over-Week Comparison:** Shows percentage changes in revenue and other metrics.
- **AI-Powered Reporting:** Uses OpenAI to turn calculated results into clear business insights.
- **Accurate Calculations:** Performs numerical calculations in JavaScript and uses AI for report writing.
- **Error Handling:** Handles empty datasets and division-by-zero cases.
- **Professional Email Reports:** Delivers a structured HTML report directly to the founder.
- **Automated Scheduling:** Runs every Monday at 9 AM without manual intervention once configured.
- **Failure Notifications:** Sends an alert through a separate error workflow when a failure is captured.

## 🛠️ Technologies Used

| Component | Technology |
|---|---|
| Workflow Automation | n8n |
| Data Source | Google Sheets |
| Data Processing | JavaScript |
| AI Report Generation | OpenAI GPT-4o-mini |
| Conditional Logic | n8n IF Node |
| Report Formatting | Markdown to HTML |
| Email Delivery | Gmail |
| Error Monitoring | n8n Error Trigger |

## 📊 Sample Report Structure

The generated weekly sales report includes:

1. Executive Summary
2. Key Performance Indicators (KPIs)
3. Week-over-Week Performance Comparison
4. Best-Performing Products and Customers
5. Sales Representative and Regional Performance
6. Payment Status Analysis
7. Business Insights and Risks
8. Actionable Recommendations

## 🚀 Setup Instructions

### 1. Import the Workflow
Import the n8n workflow JSON file into your n8n instance.

### 2. Connect Credentials
Configure your credentials for:
- Google Sheets
- Gmail
- OpenAI

### 3. Configure the Sales Sheet
Select your Google Spreadsheet and specify the sheet containing your sales records.

### 4. Configure Email Delivery
Set the founder's email address in the Gmail node.

### 5. Configure Scheduling
Set the Schedule Trigger to run every Monday at 9 AM. Ensure your n8n timezone is configured correctly.

### 6. Activate the Workflow
Test the workflow with sample sales data, verify the calculations and email output, and activate it.

Reports will then be generated automatically according to the configured schedule.

## 💼 Business Value

This automation helps businesses:

- Reduce manual sales reporting.
- Monitor weekly business performance.
- Identify sales trends and top performers.
- Detect potential payment and sales issues.
- Make faster, data-driven decisions.

## 👨‍💻 Portfolio Project

This project demonstrates practical skills in **n8n workflow automation, JavaScript data processing, Google Sheets integration, AI-powered reporting, KPI analysis, and automated email delivery**.

