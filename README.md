📈 Automated Weekly Sales Report
An n8n automation that reads sales data from Google Sheets, analyzes it, and emails a professional AI-written weekly report to the founder — every Monday at 9 AM, hands-free.

Built as part of a finance-automation portfolio.

🎯 What it does
Every Monday morning, this workflow:

Reads the latest sales data from a Google Sheet
Analyzes the last 7 days — revenue, orders, units, top product / customer / rep / region, and payment status
Compares this week vs last week (week-over-week % change, e.g. Revenue ▲ 12% vs last week)
Generates a clean, CEO-ready report using AI (GPT-4o-mini)
Emails it as formatted HTML to the founder's inbox
If there's no data for the week, it sends a short "no data" notice instead of a broken report. If the workflow ever fails, a separate error-alert workflow emails a warning.

🧩 How it works
Every Monday 9AM (Schedule Trigger)
        │
        ▼
Read Sales Data (Google Sheets)
        │
        ▼
Analyze & Build Report (Code node)
        │
        ▼
     Has Data? (IF)
     ┌──────┴───────┐
   true            false
     │                │
     ▼                ▼
Message a model    "No data
  (OpenAI)          this week"
     │              email
     ▼
  Markdown → HTML
     │
     ▼
 Email Founder (Gmail)
✨ Key features
Week-over-week comparison — trend line (▲/▼ %) at the top of every report
Math done in code, words done by AI — numbers are always accurate; AI only phrases them
Edge-case safe — handles empty sheets and divide-by-zero gracefully
Professional HTML email — Markdown converted to clean formatting
Error alerting — a linked error workflow notifies on any failure
Fully scheduled — zero manual effort once live
🛠️ Tech / Nodes used
Component	Node
Trigger	Schedule Trigger (weekly, Mon 9 AM)
Data source	Google Sheets
Analysis	Code node (JavaScript)
Branching	IF node
AI report	OpenAI (GPT-4o-mini)
Formatting	Markdown → HTML
Delivery	Gmail
Reliability	Error Trigger workflow
📊 Sample report structure
📈 Executive Summary (with week-over-week trend line)
Key Performance Indicators
Best Performers
Payment Status Analysis
Sales Insights
Business Risks
Recommendations
🚀 Setup
Import the workflow into your n8n instance
Connect your Google Sheets, Gmail, and OpenAI credentials
Point the Google Sheets node at your sales sheet
Set the recipient email in the Gmail node
Publish — reports start arriving every Monday at 9 AM

