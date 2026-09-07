### 📊 BigQuery Cost Observability

A Python-based analytics project focused on analyzing BigQuery job data to understand data processing consumption, usage patterns, and query performance.

#### 🎯 Overview

The project analyzes BigQuery job-level data to identify consumption patterns across time, projects, and users, while also evaluating the relationship between processing volume and query execution time.

The analysis was developed using Python and Pandas, with Matplotlib used for data visualization.

#### 💡 Business Questions

The analysis focuses on questions such as:

* How does BigQuery processing consumption vary over time?
* Which projects account for the highest processing volumes?
* How is processing consumption distributed across users?
* Does processing a larger volume of data generally result in longer query execution times?

#### 🔎 Approach

The project follows a structured analytics workflow:

1. **Data Loading** — Load the BigQuery job dataset using Pandas.
2. **Data Profiling** — Inspect the dataset structure, dimensions, columns, and data types.
3. **Data Type Standardization** — Convert timestamp fields into appropriate datetime types.
4. **Data Quality** — Validate completeness, uniqueness, and business rules across key fields.
5. **Data Transformation** — Create analytical fields such as monthly periods and query duration.
6. **Analysis** — Analyze processing consumption by month, project, and user, as well as query performance.

#### 🧪 Data Quality

The dataset was validated using both structural and business-rule checks, including:

* Null value validation
* Duplicate job ID validation
* Timestamp consistency
* Non-positive processing and billing values
* Billing volume exceeding processed volume
* Cache-hit billing consistency
* Valid slot usage

No violations were identified under the defined validation rules.

#### 🗂️ Dataset

The project uses a mock dataset representing BigQuery job activity during 2025.

The dataset contains **100,000 job records** and includes fields related to:

* Job and user information
* Project information
* Query execution timestamps
* Statement types
* Bytes processed and billed
* Slot usage
* Cache hits
* Job state

#### 🛠️ Technologies

* **Python**
* **Pandas**
* **Matplotlib**

#### 📁 Project Structure

```text
bigquery_cost_observability/
│
├── BigQuery_Cost_Observability.ipynb
├── README.md
└── data/
    └── bigquery_jobs_2025_mock_sample.csv
```

#### ▶️ How to Run

Open `BigQuery_Cost_Observability.ipynb` in Jupyter Notebook or Google Colab and run the cells sequentially.
