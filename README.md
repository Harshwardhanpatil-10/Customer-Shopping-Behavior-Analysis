# Customer-Shopping-Behavior-Analysis
E-commerce customer behavior analysis using Python, SQL, and Power BI with data insights and interactive dashboard visualization.
# Customer Shopping Behavior Analysis

## Project Overview
This project analyzes customer purchasing behavior in an e-commerce environment using **Python, SQL, and Power BI**. The goal is to extract insights about customer spending patterns, product popularity, discount usage, and subscription behavior.

The project includes **data cleaning, exploratory data analysis (EDA), SQL business queries, and an interactive Power BI dashboard** to visualize insights.

---

## Objectives
- Analyze customer purchasing patterns
- Identify high revenue customer segments
- Study the impact of discounts on purchases
- Compare spending behavior of subscribers and non-subscribers
- Identify top performing products
- Build an interactive Power BI dashboard

---

## Dataset
The dataset contains customer shopping behavior information.

### Main Features

| Column | Description |
|------|-------------|
| Customer_ID | Unique identifier for each customer |
| Gender | Gender of customer |
| Age | Customer age |
| Category | Product category |
| Item_Purchased | Product purchased |
| Purchase_Amount | Amount spent |
| Discount_Applied | Whether discount was used |
| Review_Rating | Product rating |
| Shipping_Type | Type of shipping |
| Subscription_Status | Customer subscription status |
| Previous_Purchases | Number of previous purchases |
| Age_Group | Age segment of customer |

---

## Tools & Technologies
- Python
- Pandas
- Matplotlib
- Seaborn
- SQL
- Power BI
- Jupyter Notebook

---

## SQL Analysis

### Revenue by Gender
```sql
SELECT gender, SUM(purchase_amount) AS revenue
FROM customer
GROUP BY gender;
```

### Customers Using Discount but Spending Above Average
```sql
SELECT customer_id, purchase_amount
FROM customer
WHERE discount_applied = 'Yes'
AND purchase_amount >= (SELECT AVG(purchase_amount) FROM customer);
```

### Top 5 Highest Rated Products
```sql
SELECT item_purchased,
ROUND(AVG(review_rating::numeric),2) AS average_product_rating
FROM customer
GROUP BY item_purchased
ORDER BY AVG(review_rating) DESC
LIMIT 5;
```

### Average Spending by Shipping Type
```sql
SELECT shipping_type,
ROUND(AVG(purchase_amount),2)
FROM customer
WHERE shipping_type IN ('Standard','Express')
GROUP BY shipping_type;
```

---

## Power BI Dashboard
An interactive dashboard was created to visualize customer behavior and purchasing patterns.

### Dashboard Insights
- Revenue by Gender
- Top Purchased Products
- Customer Segmentation
- Discount Impact Analysis
- Subscription vs Non-Subscription Revenue
- Age Group Revenue Distribution

---

## Key Insights
- Subscribers generate higher revenue compared to non-subscribers.
- Loyal customers contribute a significant portion of revenue.
- Discounts influence purchasing behavior for certain products.
- Some product categories consistently receive higher ratings.

---

## Project Structure

```
Customer-Shopping-Behavior-Analysis
│
├── dataset
│   └── customer_shopping_behavior.csv
│
├── sql
│   └── customer_behavior_sql_queries.sql
│
├── notebook
│   └── Customer_Shopping_Behavior_Analysis.ipynb
│
├── powerbi
│   └── customer_behavior_dashboard.pbix
│
└── README.md
```

---

## How to Run the Project

Clone the repository

```
git clone https://github.com/yourusername/customer-shopping-behavior-analysis
```

Install required libraries

```
pip install pandas matplotlib seaborn
```

Run the Jupyter Notebook

```
Customer_Shopping_Behavior_Analysis.ipynb
```

---

## Future Improvements
- Customer lifetime value prediction
- Recommendation system
- Sales forecasting using machine learning
- Customer churn prediction

---

## Author
Harshvardhan Patil

Data Analytics | Python | SQL | Power BI
