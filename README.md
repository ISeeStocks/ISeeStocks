# S&P 500 Data ELT Pipeline

## Overview
This project is an automated ELT (Extract, Load, Transform) pipeline designed to process and analyze S&P 500 stock market data from 2019 to 2024. The pipeline leverages modern data tools like Google Sheets, Fivetran, Snowflake, and dbt to provide actionable insights for traders, investors, and financial analysts. The system focuses on key sectors and companies, offering a comprehensive view of market trends, profitability, volatility, and growth.

## Vision Statement
The S&P 500 Data ELT Pipeline aims to streamline the extraction, loading, and transformation of stock market data, enabling real-time processing and profitability analysis. By reducing manual workloads and improving data accuracy, the pipeline supports informed decision-making and data-driven investment strategies.

## Key Features
- **Automated Data Processing:** Efficiently extracts, loads, and transforms stock market data.
- **Comprehensive Analysis:** Provides insights into profitability, volatility, growth trends, and sector performance.
- **Real-Time Capabilities:** Enables timely decision-making with up-to-date data.
- **Scalable Architecture:** Built with cutting-edge tools like Snowflake and dbt for scalability and performance.

## Data Pipeline Architecture
The pipeline follows a Directed Acyclic Graph (DAG) structure, with the following key components:

### Dimension Tables
- `raw_data.sector_mapping`: Contains sector attributes.
- `stg_stock_prices`: Serves as both a dimension and fact table, storing stock prices and volumes.

### Fact Tables
- `raw_data.stockwatch`: Historical stock data (open, high, low, close, volume).
- Intermediate tables for metrics like daily/monthly returns, volatility, moving averages, and more.
- Final aggregated tables for stock summaries, sector analysis, trend analysis, and risk analysis.

### Entity-Relationship Diagram (ERD)
The ERD outlines the relationships between entities such as `raw_data.stockwatch`, `raw_data.sector_mapping`, and various intermediate and final tables. Key attributes include:
- `date`, `ticker`, `open`, `high`, `low`, `close`, `volume` for stock data.
- Derived metrics like `daily_return`, `monthly_return`, `price_volatility`, and `long_term_growth`.

## Business Intelligence Questions
The pipeline is designed to answer critical questions for traders and investors, such as:
- Which stocks had the highest/lowest monthly returns?
- What are the quarterly growth rates for each stock?
- Which stocks are the most volatile?
- How does trading volume correlate with price movements?
- How do different sectors perform in terms of profitability and volatility?

## Tools Used
- **Google Sheets:** Initial data extraction.
- **Fivetran:** Data loading.
- **Snowflake:** Data warehousing.
- **dbt:** Data transformation and modeling.

## Repository Structure
- `raw_data/`: Contains source data tables.
- `staging/`: Includes staging tables like `stg_stock_prices`.
- `intermediate/`: Houses transformed tables for metrics (e.g., `int_daily_returns`, `int_moving_averages`).
- `final/`: Aggregated tables for reporting (e.g., `final_stock_summary`, `final_sector_analysis`).

## How to Use
1. **Clone the repository:**
   ```bash
   git clone [repository-url]
   ```
2. **Set up the environment:**
   - Configure Snowflake and dbt credentials.
   - Ensure Fivetran is connected to the data sources.
3. **Run the pipeline:**
   - Execute dbt models to transform and load data.
   - Use the final tables for analysis and reporting.

## Contribution
Contributions are welcome! Please fork the repository and submit a pull request for any improvements or bug fixes.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

For detailed documentation, refer to the [proposal PDF](S&P%20500%20Data%20ELT%20Pipeline%20Proposal.pdf).
