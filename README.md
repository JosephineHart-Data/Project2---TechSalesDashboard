# Project 2: Tech Sales Dashboard — Excel

## Overview
I built this interactive dashboard to analyze sales 
performance data for a fictional tech company. The goal 
was to move beyond raw numbers and uncover what was 
driving revenue, where the wins were coming from, and 
where there were gaps worth addressing.

**Tools Used:** Excel (Power Query, Pivot Tables, 
Charts, Slicers)

---

## The Dataset
The raw dataset contained order-level records with 
the following columns:

- Order ID
- Date
- Customer ID
- Sales Rep
- Region
- Product
- Category
- Quantity
- Unit Price
- Discount %
- Revenue

---

## The Messy Data
Before any analysis could happen, the raw dataset had 
several quality issues that needed to be addressed:

- The Date column had three different formats in the 
  same column (e.g. 2023-12-03, January 05 2023, 
  03/16/2023)
- The Region column had extra spaces and mixed 
  capitalisation (e.g. "S outh", "WEST", "east") 
  causing the same region to appear as multiple 
  different entries
- The Product column had inconsistent capitalisation 
  (e.g. "HEADSET", "headset", "Headset") causing 
  products to be counted as separate items
- Some rows had blank Sales Rep entries which would 
  have excluded transactions from rep-level analysis
- Some Unit Price entries had currency symbols inside 
  the cell (e.g. $296.79) preventing numerical 
  calculations
- Some Discount % entries had percentage symbols 
  inside the cell (e.g. 5%) instead of plain numbers
- Some rows had missing Customer ID values

---

## Data Cleaning Process
I cleaned the raw dataset in Power Query before 
building the analysis. Here is exactly what I did 
for each issue:

**1. Standardised Date Formats**
The Date column had three different formats in the 
same column. I used Power Query's data type 
conversion to standardise all dates to a consistent 
YYYY-MM-DD format so time-based analysis would 
work correctly.

**2. Fixed Region Column**
The Region column had extra spaces and inconsistent 
capitalisation. I used the Trim function to remove 
extra spaces and applied Transform > Capitalize Each 
Word to standardise all region names to Proper Case.

**3. Fixed Product Column**
Product names appeared in different cases throughout 
the dataset. I applied Transform > Capitalize Each 
Word to standardise all product names so they grouped 
correctly in the analysis.

**4. Handled Missing Sales Rep Values**
Rows with blank Sales Rep entries were replaced with 
"Unknown Rep" using the Replace Values function in 
Power Query so no transactions were lost from 
the analysis.

**5. Cleaned Unit Price Column**
Some Unit Price entries had dollar symbols inside 
the cell. I used Replace Values to remove the $ 
symbol and then changed the column data type to 
Decimal Number so it could be used in calculations.

**6. Cleaned Discount % Column**
Some Discount % entries had percentage symbols inside 
the cell while others were plain numbers. I used 
Replace Values to remove the % symbol and 
standardised the entire column to plain numbers.

**7. Verified Data Types**
After cleaning, I reviewed all columns and corrected 
their data types — dates as Date, numbers as Decimal 
Number or Whole Number, and text as Text — before 
loading the cleaned data into the worksheet 
for analysis.

---

## The Cleaned Data
After cleaning, the dataset was consistent, complete, 
and ready for analysis:

- All dates in a single uniform format
- All region and product names standardised
- No blank Sales Rep entries
- All numeric columns free of symbols
- Correct data types applied across all columns

---

## Pivot Tables
I built multiple Pivot Tables to summarise the data 
for the dashboard:

- Monthly Revenue Trend (Date vs Revenue)
- Product by Revenue (Product vs Total Revenue)
- Discount Band Analysis (Discount Band vs Total 
  Revenue and Avg Revenue)
- Total Revenue by Sales Rep and Region
- Avg Discount % by Sales Rep and Region
- Sales Rep Performance (Total Revenue, Order Count, 
  Avg Revenue)

---

## Dashboard
The dashboard was built on a dedicated sheet pulling 
from all Pivot Tables. It includes:

**KPI Cards:**
- Total Revenue: $3,417,617
- Total Orders: 510
- Average Revenue per Order: $6,701
- Average Discount: 7%
- Top Sales Rep: Maria Santos
- Top Region: East

**Charts:**
- Monthly Revenue Trend (line chart)
- Product by Revenue (bar chart)
- Discount Band Analysis (clustered bar chart)
- Total Revenue by Sales Rep and Region 
  (clustered bar chart)
- Avg Discount % by Sales Rep and Region 
  (clustered bar chart)
- Sales Rep Performance combining Total Revenue, 
  Order Count and Avg Revenue (multi-metric bar chart)

**Interactive Slicers:**
- Product
- Region
- Sales Rep

All slicers are connected to all Pivot Tables so 
filtering one updates the entire dashboard dynamically.

---

## Business Problems Explored
- Which products were generating the most revenue?
- How were sales reps performing across 
  different regions?
- Was discounting helping sales or quietly 
  hurting margins?
- Where were the dips in monthly revenue 
  coming from?

---

## Key Insights
- Total revenue of $3,417,617 was generated across 
  510 orders at an average of $6,701 per order — 
  a healthy order value for tech products
- Maria Santos was the standout sales rep, clearly 
  pulling ahead of the rest of the team
- The East region topped all other regions in 
  revenue performance
- Laptops and Monitors were the strongest products 
  by revenue
- The average discount sat at 7% but the Discount 
  Band Analysis revealed concerning spikes in the 
  higher discount brackets
- Monthly revenue showed noticeable dips that would 
  need further investigation in a real business setting

---

## Recommendations
- Investigate the months where revenue dropped — 
  are those dips tied to specific reps, products, 
  or regions?
- Study what Maria Santos is doing differently and 
  explore what can be replicated across the wider team
- Put a closer eye on high discount activity — 
  anything above 15% needs a clear business 
  justification
- The East region strategy is working — identify 
  what is different there and apply those learnings 
  to underperforming regions

---

## Dashboard Preview

![Dashboard Overview](https://raw.githubusercontent.com/JosephineHart-Data/Project2---TechSalesDashboard/main/Screenshot%202026-04-20%20135627.png)





---

## How to Use
1. Download the Excel file
2. Enable editing if prompted
3. Navigate to the **Dashboard** sheet
4. Use the slicers to filter by Product, Region, 
   or Sales Rep
5. All charts update dynamically based on 
   your selection

---

## Connect With Me
- 💼 LinkedIn: linkedin.com/in/josephinehart-n 
- 🐙 GitHub: github.com/JosephineHart-Data
- 📊 Brand: datawithjosephine

---

*This is Project 2 of my data analytics portfolio.
Project 1 — Decoding Credit Risk: A Data-Driven 
Lending Analysis using SQL, Excel and Power BI 
— is also available on my GitHub.*

