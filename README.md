# HCL_Hackathon
📘 Customer Loyalty Analytics & Segmentation System
A complete data ingestion, quality validation, loyalty points, RFM, segmentation & visualization pipeline built using Python, Pandas, and SQLite

📌 Table of Contents
Project Summary


Objectives


Key Features


Tech Stack


Data Flow


Important Formulas


Database Tables Created


Segmentation Logic


Visualization Output


How to Run


Future Enhancements


Author



📌 Project Summary
This project implements a real-world retail loyalty data pipeline that reads transactional customer data from a CSV file, validates it, stores it in a database, awards loyalty points, calculates RFM metrics, segments customers, identifies unknown customers, and visualizes insights to support marketing and retention strategies.

🎯 Objectives
✔ Ensure clean, validated, structured data
 ✔ Reward customers using loyalty rules
 ✔ Measure customer value mathematically
 ✔ Identify churn-risk customers
 ✔ Separate unknown vs known customers
 ✔ Provide business-ready insights via analytics

🚀 Key Features
Feature
Description
Data ingestion
Load raw data from CSV
Data quality checks
Validate required columns and formats
Clean & reject split
Accepted → DB, Rejected → error log
Loyalty points
Points earned per transaction
Points balance update
Maintain current balance per customer
RFM metrics
Recency, Frequency, Monetary
Segmentation
High-Spender, At-Risk, Regular
Unknown customers
new_customer entity
Analytics & charts
Business insights & visualization


🛠 Tech Stack
Component
Technology
Language
Python
Libraries
Pandas, NumPy, Matplotlib, Seaborn
Database
SQLite, SQLAlchemy
Notebook
Jupyter Lab


🔄 Data Flow
Raw CSV
   │
   ▼
 Data Type Conversion
   │
   ▼
 Data Quality Validation
   │
   ├──────────────► Rejected Data → rejected_records table
   ▼
 Clean Data
   │
   ▼
 transactions table
   │
   ▼
 customer_details table
   │
   ▼
 Loyalty Points Calculation → loyalty_transactions table
   │
   ▼
 Total Points Update (Customer Level)
   │
   ▼
 RFM Calculation → rfm_metrics table
   │
   ▼
 Segmentation → customer_segments table
   │
   ▼
 Unknown Customer Detection → new_customer table
   │
   ▼
 Visualizations & Insights


🔢 Important Formulas
Metric
Formula
Meaning
Loyalty Points
points = Total_Amount // 100
1 point per ₹100 spent
Total Points
sum(points)
Lifetime loyalty value
Recency
Today – Last Purchase Date
Activeness
Frequency
Count(Transactions)
Engagement
Monetary
sum(Total_Amount)
Revenue contribution
AOV
Total Spend / txn_count
Basket size
High-Spender Cutoff
90th Percentile (Monetary)
Top 10%


🗄 Database Tables Created
Table Name
Description
transactions
Valid clean transactions
rejected_records
Invalid records + error reason
customer_details
Customer profile + loyalty balance
loyalty_transactions
Points earned per transaction
rfm_metrics
RFM values for each customer
customer_segments
Final customer label
new_customer
Potential loyalty prospects


🧩 Segmentation Logic
Segment
Condition
High-Spender
Monetary >= 90th percentile
At-Risk
Recency > 30 days AND total_points > 0
Regular
Everyone else


📊 Visualization Output
Created charts include:
Donut chart (segment distribution)


RFM correlation heatmap


Monetary vs Recency scatter plot


Frequency vs Monetary bubble chart


Boxplots for Recency, Frequency, Monetary


Points vs Monetary regression analysis


These help understand customer behavior patterns and marketing actions.

▶ How to Run
Clone project


Open project folder


Launch Jupyter Lab


Install dependencies:

 pip install pandas sqlalchemy matplotlib seaborn


Run notebook cells in order


Check retail_loyalty.db for outputs



 Future Enhancements
Enhancement
Benefit
Machine Learning Churn Model
Predict likely drop-offs
Personalized Offers Engine
AI-driven reward strategy
Streamlit / PowerBI Dashboard
Real-time insights
API Integration
Works with real world apps
Email/WhatsApp Campaign Engine
Automated targeting


