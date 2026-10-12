# InsightFlow

**An End-to-End E-Commerce Analytics Project**

InsightFlow is a data analytics project built using the Brazilian E-Commerce Public Dataset by Olist. The project aims to transform raw e-commerce data into meaningful business insights through exploratory data analysis, data preparation, KPI tracking, interactive dashboards, and machine learning.

## Project Objectives

- Analyze sales performance and order trends.
- Understand customer purchasing behavior and retention.
- Evaluate product and seller performance.
- Monitor delivery performance and customer satisfaction.
- Develop an analytics dashboard to support data-driven decision-making.
- Explore machine learning opportunities to extend the analytical capabilities of the project.

## Key Business Metrics

- Total Product Revenue
- Total Orders
- Total Customers
- Average Order Value (AOV)
- Units Sold
- Average Review Score
- Late Delivery Rate
- Cancellation Rate
- Repeat Customer Rate

*Metric definitions and calculation rules are documented in the business requirements.*

## Dataset

The project uses the Brazilian E-Commerce Public Dataset by Olist, which contains information about customers, orders, order items, payments, reviews, products, sellers, and geolocation.

dataset link: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

## Tech Stack

- **Programming:** Python
- **Data Analysis:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Development:** Jupyter Notebook
- **Version Control:** Git and GitHub
- **Planned:** Interactive dashboard and machine learning integration

## Project Structure

```text
InsightFlow/
├── dashboard/      # Dashboard application
├── data/
│   ├── raw/        # Original datasets (not tracked by Git)
│   └── processed/  # Processed datasets (not tracked by Git)
├── docs/
│   ├── business_requirements.md
│   ├── data_dictionary.md
│   └── erd.md
├── markdown/       # Additional project notes
├── models/         # Machine learning models
├── notebooks/
│   └── 01_olist_exploration.ipynb
├── src/            # Reusable source code
├── .gitignore
├── requirements.txt
└── README.md
```

## Current Progress

### Sprint 1: Project Foundation and Data Exploration

- [x] Dataset acquisition
- [x] Exploratory data analysis
- [x] Business questions and KPI definition
- [x] Entity Relationship Diagram (ERD)
- [x] Data dictionary
- [x] Repository and Python environment setup

### Upcoming Work

- Data cleaning and validation
- Data transformation and feature engineering
- Analytical data modeling
- Dashboard development
- Machine learning integration
- Testing and documentation

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/andiraputri761-tech/insightflow.git
cd insightflow
```

### 2. Create and activate a virtual environment

Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the dataset

Download the Brazilian E-Commerce Public Dataset by Olist and place the CSV files inside `data/raw/`.

### 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `notebooks/01_olist_exploration.ipynb` to explore the dataset.

## Documentation

- [Business Requirements](docs/business_requirements.md)
- [Data Dictionary](docs/data_dictionary.md)
- [Entity Relationship Diagram](docs/erd.md)

## Project Status

Currently in development. Dashboard and machine learning components are planned for future iterations.

## Author

**Andira Putri Nirmala**

Aspiring Data Analyst with interests in data analytics, business intelligence, and machine learning.
