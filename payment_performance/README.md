### 📊 Payment Performance & Merchant Insights

A Python-based analytics project focused on analyzing payment transaction data to understand approval rates, merchant performance, payment channel differences, and changes in transaction outcomes over time.

#### 🎯 Overview

The project analyzes synthetic payment transaction data to identify performance patterns across merchants, channels, and time periods, with a particular focus on understanding changes in payment approval rates.

The analysis was developed using Python and Pandas, with Matplotlib used for data visualization. Findings are translated into potential areas for business investigation and monitoring.

#### 💡 Business Questions

The analysis focuses on questions such as:

* What is the overall payment approval rate?
* Which merchants have below-average approval rates?
* How does approval performance differ across payment channels?
* How do approval rates change over time?
* Which merchants experienced the largest approval-rate declines between June–July and August–September 2026?

#### 🔎 Approach

The project follows a structured analytics workflow:

1. **Data Loading** — Load the synthetic transaction dataset using Pandas.
2. **Data Profiling** — Inspect dataset structure, dimensions, columns, and data types.
3. **Data Type Standardization** — Convert transaction timestamps into appropriate datetime types.
4. **Data Quality** — Check missing values, duplicate transaction IDs, available statuses and channels, and non-positive transaction amounts.
5. **Data Transformation** — Create analytical fields such as transaction month, approval flags, and approved transaction amounts.
6. **Analysis** — Calculate overall approval rates, build merchant KPIs, compare payment channels, examine monthly trends, and investigate merchant-level changes between two periods.
7. **Key Findings & Recommendations** — Summarize findings, potential business implications, investigation priorities, and monitoring metrics.

#### 🧪 Data Quality

The dataset was assessed using structural and business-rule checks, including:

* Null value validation
* Duplicate and unique transaction ID validation
* Transaction status and payment channel inspection
* Non-positive transaction amount checks

The analysis identified 502 missing values in `card_country` and no duplicate transaction IDs. Missing country values were retained rather than assigned an unsupported value.

#### 🗂️ Dataset

The project uses a **synthetic dataset of 100,000 payment transaction attempts**, including fields related to:

* Transaction and merchant identifiers
* Transaction timestamps
* Transaction amounts in CAD
* Transaction status
* Payment channel
* Card country

The dataset is simulated and does not contain real transaction data.

#### 📈 Key Findings & Recommendations

* **Overall performance:** The overall payment approval rate was approximately **84.23%**, providing a baseline for comparisons across merchants, channels, and months.
* **Channel performance:** E-commerce had the lowest approval rate (**80.42%**), compared with POS (**87.99%**) and Mobile (**85.63%**). It accounted for approximately **57% of all declines**, making it a useful starting point for further investigation.
* **Monthly trend:** Approval rates declined from approximately **84.63% in June–July** to **82.23% in August–September 2026**, a decrease of approximately **2.39 percentage points**.
* **Merchant performance:** Among merchants with at least 30 attempts in both comparison periods, M00784 and M00430 experienced approval-rate decreases exceeding 21 percentage points. Their relatively small volumes mean these changes do not necessarily explain the overall decline.

**Recommended next steps:** Investigate E-commerce performance by merchant and other available dimensions; prioritize merchant and channel investigations using both approval-rate changes and transaction volumes; and incorporate decline reason codes and operational context where available.

**Suggested monitoring metrics:** Overall approval rate, approval rate by channel, merchant approval rate, and declined transaction volume.

#### ⚠️ Limitations

* The dataset is synthetic.
* The analysis identifies patterns and investigation priorities, not proven root causes of transaction declines.
* Decline reason codes and operational incident data are not included in the analyzed transaction dataset, limiting causal interpretation.
* Merchant comparisons focus on merchants present in both periods; a separate analysis would be needed to assess entry and exit effects comprehensively.
* The 30-attempt threshold is an exploratory filter, not a statistical significance test.

#### 🛠️ Technologies

* **Python**
* **Pandas**
* **Matplotlib**

#### 📁 Project Structure

```text
payment_performance/
│
├── Payment_Performance.ipynb
├── README.md
└── data/
    └── transactions.csv
```

#### ▶️ How to Run

Open `Payment_Performance.ipynb` in Jupyter Notebook or Google Colab and run the cells sequentially.

**← [Back to main README](../README.md)**
