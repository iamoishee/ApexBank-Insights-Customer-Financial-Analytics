# Banking Data Analysis - Exploratory Data Analysis (EDA) Case Study

A comprehensive exploratory data analysis of banking customer data, examining customer demographics, financial behaviors, and account characteristics to uncover actionable business insights.

## Project Overview

This project performs an in-depth exploratory data analysis (EDA) on a banking dataset containing customer information, account details, and financial metrics. The analysis reveals patterns in customer behavior, financial accumulation trends, and relationships between various banking variables.

**Key Objectives:**
- Understand customer demographics and distribution
- Analyze financial behavior patterns and account relationships
- Identify correlations between banking variables
- Segment customers based on income and other characteristics
- Provide actionable insights for business strategy

## Dataset Description

The dataset comprises **25 customer attributes** across two main tables:

### Customers Table
| Column | Description | Type |
|--------|-------------|------|
| Client_ID | Unique customer identifier | String |
| Name | Customer name | String |
| Age | Customer age | Integer |
| Location_ID | Branch/location identifier | Integer |
| Joined_Bank | Customer onboarding date | Date |
| Banking_Contact | Primary banking contact | String |
| Nationality | Customer nationality | String |
| Occupation | Customer occupation | String |
| Fee_Structure | Customer fee tier | Categorical |
| Loyalty_Classification | Loyalty program tier | Categorical |
| Estimated_Income | Annual estimated income | Float |
| Superannuation_Savings | Retirement savings | Float |
| Amount_of_Credit_Cards | Number of credit cards held | Integer |
| Credit_Card_Balance | Outstanding credit card balance | Float |
| Bank_Loans | Total bank loan amount | Float |
| Bank_Deposits | Total deposits | Float |
| Checking_Accounts | Checking account balance | Float |
| Saving_Accounts | Savings account balance | Float |
| Foreign_Currency_Account | Foreign currency holdings | Float |
| Business_Lending | Business loan amount | Float |
| Properties_Owned | Number of properties | Integer |
| Risk_Weighting | Customer risk score | Categorical |
| BRId | Banking Reference ID | Integer |
| GenderId | Gender identifier | Integer |
| IAId | Investment Account ID | Integer |

**Dataset Size:** Complete dataset with no missing values  
**Data Quality:** Clean, validated, and ready for analysis

## Project Structure

```
Banking Data Analysis/
│
├── Banking_EDACaseStudy.ipynb      # Main analysis notebook
├── BankEDA (Version 1).ipynb       # Previous analysis iteration
├── BankEDA (Version 2).ipynb       # Alternative analysis version
│
├── data/
│   ├── Banking.csv                 # Banking dataset CSV
│   └── clients.csv                 # Client information CSV
│
└── README.md                        # This file
```

## Getting Started

### Prerequisites

- Python 3.7 or higher
- SQL Server (for database connection) or use CSV files
- Jupyter Notebook or JupyterLab

### Required Libraries

```bash
pip install pandas numpy matplotlib seaborn pyodbc sqlalchemy
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/banking-data-analysis.git
cd banking-data-analysis
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Configure database connection (if using SQL Server):
   - Update connection string in the notebook with your server details
   - Replace `Server=LOOPER\SQLEXPRESS` with your SQL Server instance

## 📈 Analysis Sections

### 1. **Data Import & Connection**
- SQL Server database connection setup
- Data retrieval and initial exploration
- Data shape and structure verification

### 2. **Data Cleaning & Preparation**
- Missing value detection and handling
- Date format conversion for temporal analysis
- Income band categorization (Low/Medium/High)

### 3. **Categorical Analysis**
- Distribution analysis of 11 categorical variables
- Univariate analysis with countplots
- Value counts for all categorical features

### 4. **Numerical Analysis**
- Histogram distributions with KDE curves
- Descriptive statistics for 11 numerical variables
- Identification of outliers and distribution patterns

### 5. **Correlation Analysis**
- Correlation matrix for all numerical features
- Heatmap visualization with color-coded relationships
- Identification of strong positive/negative correlations

### 6. **Bivariate Analysis**
- Cross-tabulation across demographic segments
- Categorical relationships with nationality segmentation
- Scatter plots with regression lines for key variable pairs

### 7. **Key Insights & Findings**
- Pattern identification and business implications
- Customer segmentation opportunities
- Risk assessment indicators

## 🔍 Key Findings

### Deposits and Savings Behavior
- **Strong correlation** between Bank Deposits and Saving Accounts (r ≈ 0.85)
- Customers who maintain high balances in one account typically hold substantial funds across other accounts
- Suggests complementary account management strategies

### Income, Age, and Financial Accumulation
- **Moderate positive correlations** between Age and Superannuation Savings
- Higher income earners accumulate more savings, retirement funds, and loan balances
- Reflects typical financial lifecycle patterns

### Property Ownership
- **Weak correlations** with banking variables indicate property ownership depends on external factors
- Real estate market conditions and location matter more than banking behavior
- Properties owned serve as alternative wealth storage

### Business vs. Personal Banking
- **Moderate correlation** between Business Lending and Bank Loans
- Some customers maintain distinct business and personal banking segments
- Business lending serves a specialized customer subset

### Nationality-Based Patterns
- **Diverse customer base** across multiple nationalities
- Different nationalities exhibit distinct banking behaviors
- Nationality influences financial preferences and risk profiles

### Income Band Distribution
- Customers segmented into Low, Medium, and High income bands
- Income band serves as primary segmentation variable
- Strong predictor of financial behavior and credit utilization

## 📊 Visualizations Included

- **Countplots:** Distribution of categorical variables
- **Histograms with KDE:** Distribution patterns of numerical features
- **Correlation Heatmap:** Relationship matrix between numerical variables
- **Regression Plots:** Bivariate relationships with trend lines
- **Bar Charts:** Income band and categorical comparisons

## 💡 Business Recommendations

1. **Customer Segmentation**
   - Create 4-5 distinct customer profiles based on income, age, and account types
   - Tailor products and services to each segment

2. **Risk Assessment**
   - Develop credit risk models using correlation patterns
   - Leverage Risk_Weighting with loan and credit metrics

3. **Geographic Analysis**
   - Analyze BRId patterns to understand branch performance
   - Identify high-performing and underperforming locations

4. **Temporal Analysis**
   - Track customer acquisition trends using Joined_Bank field
   - Measure customer lifecycle value over time

5. **Fee Structure Optimization**
   - Compare customer behaviors across fee tiers
   - Assess pricing strategy effectiveness

6. **Predictive Modeling**
   - Build churn prediction models
   - Forecast customer lifetime value
   - Identify high-risk credit customers

7. **Business Development**
   - Target high-potential customers for business lending
   - Cross-sell opportunities across product lines

## 🔗 Database Connection

### SQL Server Setup (Optional)
```python
import pyodbc

conn = pyodbc.connect('Driver={ODBC Driver 17 for SQL Server};'
                      'Server=YOUR_SERVER;'
                      'Database=banking_case;'
                      'Trusted_Connection=yes;')
cursor = conn.cursor()
```

### Alternative: CSV Import
```python
import pandas as pd

df = pd.read_csv('data/Banking.csv')
```

## 📝 Usage

1. Open the main notebook:
```bash
jupyter notebook Banking_EDACaseStudy.ipynb
```

2. Execute cells sequentially to reproduce the analysis

3. Modify queries or filters as needed for custom analysis

4. Export visualizations and insights for presentations

## 📂 Data Files

- **Banking.csv** - Main customer and account dataset
- **clients.csv** - Client reference information

## 🛠️ Technologies Used

- **Python 3.x** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **Matplotlib** - Static visualizations
- **Seaborn** - Statistical data visualization
- **Pyodbc** - SQL Server database connection
- **Jupyter Notebook** - Interactive analysis environment

## 📚 Analysis Outputs

The notebook generates:
- Detailed statistical summaries
- 30+ publication-quality visualizations
- Correlation matrices
- Customer segmentation insights
- Business intelligence findings

## ✅ Data Quality

- **No missing values** detected across all columns
- **Complete dataset** with full customer records
- **Validated data types** for accurate analysis
- **Clean format** ready for modeling and reporting

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📧 Contact & Support

For questions or support regarding this analysis:
- Create an issue on GitHub
- Reach out through the project repository

## 🙏 Acknowledgments

- Banking dataset provided by [www.kaggle.com]
- Analysis methodologies based on industry best practices
- Visualization techniques from Seaborn and Matplotlib documentation

## 📖 References

- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Gallery](https://seaborn.pydata.org/examples.html)
- [Python Data Analysis Best Practices](https://realpython.com/)

---

**Last Updated:** May 2, 2026  
**Project Status:** ✅ Complete and Ready for Deployment  
**Version:** 1.0.0
