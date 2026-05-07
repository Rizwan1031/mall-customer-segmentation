# 🛍️ Mall Customer Segmentation & Clustering

> A complete end-to-end Data Science project covering data ingestion, cleaning, exploratory analysis, machine learning clustering, and business intelligence dashboard reporting for shopping mall customer behavior analysis.

---

## 📌 Project Overview

This project analyzes customer behavior across multiple shopping malls to identify distinct customer segments using unsupervised machine learning (K-Means Clustering). The insights are presented through an interactive Power BI dashboard for business decision-making.

**Dataset Size:** ~99,457 customer transaction records  
**ML Model:** K-Means Clustering (4 segments)  
**Tools Used:** Python, pandas, scikit-learn, matplotlib, seaborn, Power BI

---

## 🗂️ Project Structure

```
Mall-Customer-Segmentation/
│
├── 📁 Data/
│   ├── customer_data.xlsx          # Raw customer data (source file 1)
│   ├── sales_data.xlsx             # Raw sales/transaction data (source file 2)
│   ├── customer_data.csv           # Converted & cleaned customer data
│   ├── sales_data.csv              # Converted & cleaned sales data
│   ├── mall_customer_data.csv      # Merged master dataset
│   └── customer_segments.csv       # Final segmented output
│
├── 📁 Notebooks/
│   ├── data_cleaning.ipynb         # Step 2: Data cleaning & merging
│   ├── EDA.ipynb                   # Step 3: Exploratory Data Analysis
│   └── modeling.ipynb              # Step 5: ML Clustering Model
│
├── 📁 Dashboard/
│   ├── customer_segment_dashboard.pbix   # Customer segmentation Power BI report
│   └── shopping_mall_visuals.pbix        # Sales & mall performance visuals
│
└── README.md
```

---

## 🔄 Project Workflow

### Step 1 — Data Collection & Format Conversion
- Sourced two raw Excel files: **`customer_data.xlsx`** (customer demographics) and **`sales_data.xlsx`** (transaction records)
- Converted both `.xlsx` files into `.csv` format using pandas for easier processing downstream

**Key columns — `customer_data`:** `customer_id`, `gender`, `age`, `payment_method`  
**Key columns — `sales_data`:** `invoice_no`, `customer_id`, `category`, `quantity`, `invoice_date`, `price`, `shopping_mall`

---

### Step 2 — Data Cleaning & Merging (`data_cleaning.ipynb`)
- Handled missing values:
  - `age` column filled with **mean imputation**
  - `invoice_date` filled with **mode imputation**
- Checked and removed **duplicate invoice records**
- Merged both cleaned CSV files into a single master dataset: **`mall_customer_data.csv`**
- Engineered new features: `total_revenue`, `age_group`, `month`, `year`

**Output:** `mall_customer_data.csv` — 99,457 rows × 14 columns

---

### Step 3 — Exploratory Data Analysis (`EDA.ipynb`)
Performed visual and statistical analysis to understand customer patterns:

| Analysis | Insight |
|---|---|
| Revenue by Category | Identified top-spending product categories |
| Revenue Distribution | Right-skewed with high-value outliers |
| Age Group Distribution | Pie chart showing dominant shopper demographics |
| Mall Performance | Bar chart of total revenue per shopping mall |

**Libraries used:** `pandas`, `matplotlib`, `seaborn`

---

### Step 4 — Visual Testing & Matching
- Verified EDA visuals against data expectations
- Cross-checked chart outputs with raw aggregations for accuracy
- Ensured consistency between plotted trends and summary statistics before proceeding to modeling

---

### Step 5 — ML Modeling: K-Means Clustering (`modeling.ipynb`)

**Feature Engineering (customer-level aggregation):**
- `age` — average age per customer
- `total_quantity` — total items purchased
- `total_revenue` — total spend per customer

**Pipeline:**
1. Scaled features using **StandardScaler**
2. Used **Elbow Method** (k = 1 to 10) to determine optimal clusters → **k = 4**
3. Applied **KMeans (n_clusters=4, random_state=42)**
4. Ranked clusters by mean revenue to assign business labels

**Customer Segments Identified:**

| Segment | Description |
|---|---|
| 🔴 VIP / High Spender | Highest revenue, frequent buyer |
| 🔵 Regular Buyer | Consistent mid-range spender |
| 🟢 Occasional Buyer | Infrequent, moderate spend |
| 🟠 Low Spender | Lowest revenue, rare visits |

**Output:** `customer_segments.csv` with `customer_id`, `cluster`, and `segment` label

---

### Step 6 — Dashboard & Reporting (Power BI)

Two Power BI reports created for business stakeholders:

**`customer_segment_dashboard.pbix`**
- Customer segment distribution
- Revenue contribution per segment
- Demographic breakdown by segment

**`shopping_mall_visuals.pbix`**
- Mall-wise revenue performance
- Category-level sales trends
- Monthly/yearly revenue patterns

---

## 📊 Key Results

- **4 distinct customer segments** identified from ~99K records
- **VIP / High Spender** segment drives disproportionate revenue
- Clear revenue variation across malls and product categories
- Age group analysis reveals dominant shopper demographics

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3 | Core programming |
| pandas | Data manipulation & merging |
| scikit-learn | KMeans clustering, StandardScaler |
| matplotlib / seaborn | Data visualization |
| Power BI | Interactive business dashboard |
| Jupyter Notebook | Development environment |

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/Rizwan1031/mall-customer-segmentation.git
   cd mall-customer-segmentation
   ```

2. **Install dependencies**
   ```bash
   pip install pandas scikit-learn matplotlib seaborn openpyxl
   ```

3. **Run notebooks in order**
   ```
   1. data_cleaning.ipynb
   2. EDA.ipynb
   3. modeling.ipynb
   ```

4. **Open Power BI files** in Power BI Desktop to explore dashboards

---

## 👤 Author

**Rizwan**  
Undergraduate Student | Aspiring Data Scientist  
Skills: Python · SQL · Power BI · Machine Learning  
📧 [rizwan.gawandi.1234@gmail.com]  
🔗 [LinkedIn Profile] | [GitHub Profile]

---

## 📄 License

This project is for educational and portfolio purposes.
