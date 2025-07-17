# Lab 6: Association Rule Mining with Apriori and FP-Growth

**Course:** MSCS 634 – Data Mining  
**Student Name:** Vishnu Mallam  
**Lab Title:** Association Rule Mining with Apriori and FP-Growth  


---

## 1. Project Description

This lab focuses on extracting meaningful patterns and associations from a real-world retail transaction dataset using two popular algorithms: **Apriori** and **FP-Growth**. The objective is to identify frequent itemsets and generate association rules to understand customer purchasing behavior. The insights obtained can guide decision-making in areas such as:

- Marketing
- Inventory control
- Recommendation systems

---

## 2. Dataset Description

- **Dataset Name:** Online Retail  
- **Source:** UCI Machine Learning Repository  
- **Description:**
  - Contains transactions between `01/12/2010` and `09/12/2011` for a UK-based online retailer.
  - Key attributes: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.

- **Preprocessing Steps:**
  - Removed null/missing values
  - Filtered transactions to only include those from the **United Kingdom**
  - Excluded canceled orders and negative quantities
  - Created a **basket matrix** for market basket analysis

---

## 3. Tools and Libraries Used

- **Python** (Jupyter Notebook)
- `pandas`
- `mlxtend` (for Apriori, FP-Growth, and rule generation)
- `matplotlib` and `seaborn` (for visualization)
- `openpyxl` (to load Excel file)

---

## 4. Methodology

### Step 1: Data Preparation
- Cleaned and filtered the dataset
- Created a transaction-item matrix (one-hot encoding per invoice)

### Step 2: Exploratory Data Analysis
- Identified **top 10 most frequent items** using bar plots

### Step 3: Frequent Itemset Mining
- **Apriori Algorithm**
  - Minimum support: `0.02`
  - Generated frequent itemsets
- **FP-Growth Algorithm**
  - Minimum support: `0.02`
  - More efficient than Apriori

### Step 4: Association Rule Generation
- Minimum confidence: `0.5`
- Calculated metrics: `support`, `confidence`, `lift`
- Visualized **confidence vs lift**

---

## 5. Key Results

- Most frequent item: **WHITE HANGING HEART T-LIGHT HOLDER**
- Strong associations between **decorative home products**
- **FP-Growth** outperformed Apriori in speed and memory usage
- High lift values (> 2) indicate **strong bundling opportunities**

---

## 6. Business Use Cases

- Product Recommendation Systems  
- Shelf/Website Layout Optimization  
- Inventory Management and Forecasting  
- Customer Basket Analysis for Promotions  

---

## 7. Performance Comparison

| Metric         | Apriori | FP-Growth |
|----------------|---------|-----------|
| **Speed**      | Slower  | Faster    |
| **Memory Usage** | Higher  | Lower     |
| **Scalability** | Limited | High      |

---

## 8. Challenges and Solutions

- **Handling Frozensets in Plots**: Converted frozensets to strings for visualization
- **Computational Bottlenecks with Apriori**: Reduced dataset size and support threshold
- **Sparse Matrix Transformation**: Used `groupby` and `unstack` to create the basket matrix

---

## 9. Files Submitted

- `Lab6_Association_Rule_Mining.ipynb` – Python notebook with code and output  
- `Online Retail.xlsx` – Original dataset  
- `README.md` – This documentation  

---

## 10. Conclusion

This lab demonstrated the practical application of **Apriori** and **FP-Growth** algorithms in mining frequent itemsets and association rules. The results provided **actionable insights** into product co-purchasing behavior. FP-Growth proved more **efficient and scalable**, making it the preferred choice in real-world, large-scale applications.

---
