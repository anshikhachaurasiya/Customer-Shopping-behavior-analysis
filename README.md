# Customer Shopping Behavior Analysis

An end-to-end data analytics project analyzing 3,900 customer purchase records to uncover spending patterns, customer segments, product performance, and subscription insights — from raw data to an interactive Power BI dashboard.

## Overview

This project explores customer shopping behavior using a real-world-style retail dataset. The workflow covers the full analytics lifecycle: data cleaning and EDA in Python, business-question analysis in SQL, and visual storytelling through a Power BI dashboard and a summary presentation. The goal is to identify what drives revenue, which customer segments matter most, and where discounting and subscriptions are helping (or hurting) the business.

## Dataset

- **Size:** 3,900 rows × 18 columns
- **Contents:** Customer demographics, purchase details (category, item, amount), behavioral fields (subscription status, discount usage, review ratings), and shipping/payment information
- **Data quality:** 37 missing values in `Review Rating`, imputed using the category-level median

## Tools & Technologies

- **Python** (pandas) — data loading, cleaning, and exploratory data analysis
- **SQL** (PostgreSQL / MySQL / SQL Server) — business-question querying on the cleaned dataset
- **Power BI** — interactive dashboard and visualization
- **Gamma** — presentation deck summarizing the analysis and findings

## Project Steps

1. **Data Loading & EDA (Python)**
   - Loaded the dataset with pandas; profiled it using `.info()` and `.describe()`
   - Imputed missing `Review Rating` values using category-wise median
   - Standardized column names to `snake_case`
   - Engineered new features: `age_group` and `purchase_frequency_days`
   - Dropped the redundant `promo_code_used` column (superseded by `discount_applied`)
   - Loaded the cleaned dataset into a SQL database (PostgreSQL) for querying

2. **SQL Analysis**
   - Revenue breakdown by gender
   - Subscriber vs. non-subscriber comparison (average spend and total revenue)
   - Customer segmentation: Loyal, Returning, and New customers
   - Top products by rating and by order volume
   - Identification of high-spending customers who still use discounts
   - Discount dependency by product category
   - Payment method and purchase frequency trends

3. **Dashboard Design (Power BI)**
   - Built an interactive dashboard with filters for subscription status, gender, category, and shipping type
   - Visualized revenue and sales by product category and age group
   - Highlighted key metrics via KPI cards

4. **Reporting & Presentation**
   - Compiled findings into a structured analytical report
   - Designed a recruiter-friendly summary presentation using Gamma

## Dashboard

The Power BI dashboard includes:

| KPI | Value |
|---|---|
| Number of Customers | 3.9K |
| Average Review Rating | 3.75 |
| Average Purchase Amount | $59.76 |
| Subscriber Share | 27% |

**Key visuals:**
- % of customers by subscription status (donut chart)
- Revenue and sales by product category
- Revenue and sales by age group
- Interactive filters: subscription status, gender, category, shipping type

## Results & Key Insights

- **Revenue by gender:** Male customers generated ~$157,890 vs. ~$75,191 from female customers
- **Subscribers vs. non-subscribers:** Non-subscribers drive the bulk of revenue (~$170,436 vs. ~$62,645), though subscribers have a comparable average spend (~$59.49 vs. ~$59.87)
- **Customer segments:** Loyal customers dominate the base (3,116), followed by Returning (701) and New (83) — retention is clearly working, but new customer acquisition is low
- **Top-rated products:** Gloves, Sandals, Boots, Hats, and Skirts lead in customer satisfaction
- **Best-selling categories:** Clothing leads in both revenue and sales, followed by Accessories, Footwear, and Outerwear
- **Discount behavior:** 839 customers used discounts while still spending above average, showing discounts don't always signal price sensitivity; Hats, Sneakers, and Coats are the most discount-dependent items
- **Demographics:** Young Adults generate the highest revenue and sales among all age groups
- **Payment & frequency:** PayPal is the most common payment method; "Every 3 Months" is the most common purchase frequency

## Recommendations

- **Boost Subscriptions** — promote exclusive subscriber benefits to grow this segment's revenue share
- **Strengthen Loyalty Programs** — reward repeat buyers to further grow the Loyal segment
- **Review Discount Strategy** — balance sales lift against margin control for discount-dependent items
- **Optimize Product Positioning** — feature top-rated and best-selling items in campaigns
- **Targeted Marketing** — focus efforts on high-revenue age groups (Young Adults) and express-shipping users

## How to Run

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd customer-shopping-behavior-analysis
   ```

2. **Set up the Python environment**
   ```bash
   pip install pandas numpy sqlalchemy psycopg2
   ```

3. **Run the EDA and cleaning script**
   ```bash
   python eda_cleaning.py
   ```
   This loads the raw dataset, cleans it, engineers new features, and exports the cleaned data.

4. **Load data into your SQL database**
   - Update database credentials in the config/connection script
   - Run the load script to push the cleaned dataset into PostgreSQL/MySQL/SQL Server

5. **Run SQL queries**
   - Execute the `.sql` files in the `/sql` folder to reproduce the analysis (revenue breakdowns, segmentation, discount analysis, etc.)

6. **Open the Power BI dashboard**
   - Open the `.pbix` file in Power BI Desktop
   - Refresh the data connection to point to your database

7. **View the report and presentation**
   - Report: see `/report`
   - Presentation: see `/presentation` (built with Gamma)

## Project Structure

```
customer-shopping-behavior-analysis/
├── data/
│   └── customer_shopping_data.csv
├── eda_cleaning.py
├── sql/
│   └── analysis_queries.sql
├── dashboard/
│   └── customer_behavior_dashboard.pbix
├── report/
│   └── analysis_report.pdf
├── presentation/
│   └── customer_shopping_behavior.pdf
└── README.md
```

## Author

**Anshikha Chaurasiya**
Final-year B.Tech, Production and Industrial Engineering, NIT Jamshedpur
[GitHub](https://github.com/anshikhachaurasiya) · [LinkedIn](https://linkedin.com/in/anshikha-chaurasiya-24681328a)
