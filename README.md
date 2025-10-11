# 🛍️ Mini Project: E-Commerce Sales Data Analysis  

---

## 📘 Project Overview
This project focuses on the **comprehensive analysis of E-Commerce Sales Data** using **Microsoft Excel** and **Power BI**.  
The main objective is to **transform, model, and visualize** the raw data to derive **actionable business insights**, identify **sales trends**, and measure **performance against targets**.

---

## 📂 Source Datasets
The analysis is based on **three core datasets**:

| File Name | Description |
|------------|--------------|
| `List of Orders.csv` | Contains order-level details |
| `Order Details.csv` | Includes product, quantity, and profit data |
| `Sales Target.csv` | Provides monthly and category-wise sales target data |

---

## ⚙️ Tools & Technologies Used
- **Microsoft Excel** – Data preparation and initial exploration  
- **Power BI** – Data transformation, modeling, and interactive dashboard creation  
- **DAX (Data Analysis Expressions)** – For calculated columns and business measures  

---

## 🔄 Phase 1 – Data Transformation & Data Modeling

### **Data Import & Cleaning**
1. Imported all three CSV files into Power BI.  
2. Limited the *List of Orders* table to the **first 500 rows** for optimized analysis.  
3. Changed data types appropriately:  
   - *Order Date → Date*  
   - *Amount, Target → Fixed Decimal Number*  
4. Formatted *Customer Name* into **Proper Case** for consistency.  
5. Merged *City* and *State* columns to create a new **Location** column in the format `City, State`.  
6. Added a **Profit Margin** column using the formula:  
Profit Margin = (Profit / Amount) × 100

markdown
Copy code
7. Created a **Profit Status** column based on profit values:
- `< 0` → *Loss*  
- `= 0` → *Break-Even*  
- `> 0` → *Profit*  
8. Merged *List of Orders* and *Order Details* into a unified table **Orders Data** using *Order ID*.  
9. Identified and handled **missing values** and **duplicate rows**.  
10. **Grouped & Aggregated Metrics**:
 - Average profit by Category  
 - Total Target by Month  

### **Relationships Established**
- *List of Orders* ↔ *Order Details* → via **Order ID**  
- *Order Details* ↔ *Sales Target* → via **Category**

---

## 🧮 Phase 2 – DAX & Data Visualization

### **Calculated Columns**
| Column | Description / Formula |
|---------|-----------------------|
| **Category Type** | `'Category' & "-" & 'Sub-Category'` |
| **Revenue per Order** | `Amount × Quantity` |
| **Sales Category** | `IF(Amount > AVERAGE(Amount), "Above Average", "Below Average")` |

### **Calculated Measures**
| Measure | Formula / Description |
|----------|----------------------|
| **Order Count** | `DISTINCTCOUNT('Order Details'[Order ID])` |
| **Average Profit in Delhi** | `CALCULATE(AVERAGE('Orders Data'[Profit]), 'Orders Data'[City]="Delhi")` |
| **YTD Sales** | `TOTALYTD(SUM('Orders Data'[Amount]), 'Orders Data'[Order Date])` |

---

## 📊 Data Visualizations & Dashboards
Interactive dashboards were designed in Power BI to visualize sales and performance trends.

| Visualization | Description |
|----------------|-------------|
| **Clustered Column Chart** | Sales Target Achievement by Category |
| **Donut Chart** | Maximum Profit Margin by Sub-Category |
| **Line Chart** | Monthly Sales Trend |
| **Scatter Chart** | Profit vs Quantity by Sub-Category |
| **Cards** | Total Sales vs Target & Minimum Target per Segment |
| **Matrix Table** | Sales vs Target by Category and Month |
| **Map Visual** | Geographic Sales Analysis by City |
| **Treemap** | Sales Distribution by Sub-Category |
| **Funnel Chart** | Order Count Analysis by State |

---

## 🧠 Key Insights
- Sales performance varied across product categories, with some exceeding targets consistently.  
- **Profit margins** revealed strong performance in specific sub-categories.  
- The **“Location”** field enabled regional analysis to identify top-performing cities and states.  
- **Seasonal sales trends** were captured through monthly analysis using line charts.  
- **YTD Sales** and **Average Profit in Delhi** helped evaluate both national and regional performance.  

---

## 🪄 Summary
This project demonstrates a complete **end-to-end data analytics workflow**, covering:
- Data transformation  
- Data modeling  
- DAX calculations  
- Visual reporting using Power BI  

The analysis provided clear insights into **sales performance**, **profitability**, and **regional variations**, enhancing business decision-making through interactive dashboards.

---

## ✅ Conclusion
The **E-Commerce Sales Data Analysis Project** showcases the combined power of **Power BI** and **Excel** for practical business analytics.  
By integrating clean data models, calculated measures, and visual storytelling, this project helps:
- Track sales targets vs performance  
- Identify high-performing segments  
- Enable data-driven decision-making  

---

## 👩‍💻 Author
**Project Title:** Mini Project – E-Commerce Sales Data Analysis  
**Author:** *Umasankari Palanivel*  
**Tools:** Excel | Power BI | DAX  
**Year:** 2025  
