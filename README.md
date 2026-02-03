# Amazon Stock Price Analysis and ML Pipeline Project

This project implements a comprehensive machine learning pipeline for Amazon (AMZN) stock price analysis and prediction using AWS services. The project is structured in multiple stages, from data collection and exploration to advanced ML orchestration and deployment.

## Project Overview

The project focuses on building an end-to-end ML pipeline that:
- Collects and processes Amazon stock price data
- Performs comprehensive data exploration and analysis
- Implements predictive models using LSTM for stock price forecasting
- Deploys the solution using AWS cloud services with proper orchestration

## Dataset

The project uses Amazon (AMZN) stock price data spanning from **May 15, 1997 to April 12, 2024** (6,772 trading days), containing:

- **Open**: Opening price
- **High**: Highest price of the day
- **Low**: Lowest price of the day
- **Close**: Closing price
- **Adj Close**: Adjusted closing price
- **Volume**: Trading volume

### Data Characteristics
- **Total Records**: 6,770 entries (after processing)
- **Date Range**: 1997-2024 (27 years of data)
- **Data Quality**: No missing values, no duplicates
- **Price Range**: From $0.069792 to $189.05 (adjusted for stock splits)
- **Average Volume**: 139.1 million shares per day

## Notebooks Overview

### 1. Building Dataset (`00 - Building Dataset.ipynb`)

This notebook handles the initial data collection and preparation:

**Key Features:**
- Uses `yfinance` library to fetch Amazon stock data
- Integrates with PySpark for distributed data processing
- Converts pandas DataFrame to PySpark DataFrame for scalability
- Saves processed data to HDFS for distributed storage

**Technologies Used:**
- Python with yfinance for data collection
- PySpark for distributed data processing
- HDFS for distributed storage

**Data Processing Steps:**
1. Fetch AMZN stock data using yfinance
2. Convert to PySpark DataFrame for distributed processing
3. Store data in HDFS at `/ca3/amazon.csv`

### 2. Data Exploration (`01 - Data exploration.ipynb`)

Comprehensive exploratory data analysis using PySpark with Pandas API:

**Key Analysis:**
- **Statistical Summary**: Comprehensive descriptive statistics
- **Data Quality Assessment**: Verification of data completeness and integrity
- **Feature Engineering**: Creation of `avg_price` feature (mean of High, Low, Adj Close)
- **Temporal Analysis**: Addition of month and year columns for time-based analysis
- **Trend Visualization**: Daily and monthly stock price trend analysis

**Key Findings:**
- Stock shows strong upward trend over 27-year period
- Data exhibits non-stationary behavior (price depends on time)
- Significant price volatility with periods of rapid growth
- Clear seasonal and temporal patterns in stock performance

**Visualizations:**
- Daily stock price trends over entire period
- Monthly aggregated price movements
- Statistical distribution analysis

**Technologies Used:**
- PySpark with Pandas API for large-scale data processing
- Matplotlib and Seaborn for visualization
- HDFS for data storage and retrieval

## Current Implementation Status

This project currently includes:
- ✅ **Data Collection**: Automated fetching of Amazon stock data using yfinance
- ✅ **Data Processing**: PySpark-based distributed data processing and storage
- ✅ **Exploratory Analysis**: Comprehensive statistical analysis and visualization
- ✅ **Feature Engineering**: Creation of derived features for ML modeling
- 🔄 **AWS Implementation**: Planned (see todo.md for implementation roadmap)

## Technical Stack

### Current Implementation
- **PySpark**: Distributed data processing and analysis
- **Pandas API on Spark**: Familiar pandas interface for large-scale data
- **HDFS**: Distributed file system for data storage
- **Python**: Primary programming language with yfinance for data collection
- **Jupyter Notebooks**: Interactive data analysis and visualization

### Planned AWS Integration (see todo.md)
- **Amazon SageMaker**: Model training and deployment platform
- **MWAA (Managed Airflow)**: Workflow orchestration
- **Lambda**: Serverless data ingestion
- **S3**: Object storage for data and models
- **CloudWatch**: Monitoring and logging
- **SNS**: Notification services
- **EMR Serverless/Glue**: Advanced data processing
- **Terraform**: Infrastructure as Code
- **CodePipeline/CodeBuild**: CI/CD automation

## Data Insights

### Price Evolution
- **Starting Price** (1997): ~$0.10 (split-adjusted)
- **Peak Price**: $189.05
- **Growth**: Over 1,800x increase over 27 years
- **Volatility**: High volatility with significant price swings

### Volume Analysis
- **Average Daily Volume**: 139.1 million shares
- **Volume Range**: 9.7M to 2.1B shares
- **Liquidity**: Highly liquid stock with consistent trading activity

### Temporal Patterns
- **Long-term Trend**: Strong upward trajectory
- **Seasonality**: Monthly aggregation reveals seasonal patterns
- **Market Events**: Data captures major market events and company milestones

## Next Steps

See `todo.md` for a detailed implementation roadmap to deploy this project on AWS with full ML orchestration, monitoring, and automation capabilities.

## Getting Started

### Current Setup
1. **Prerequisites**: Python 3.8+, Apache Spark, Jupyter Notebooks
2. **Installation**: Install required packages (yfinance, pyspark, pandas, matplotlib, seaborn)
3. **Usage**: 
   - Run `00 - Building Dataset.ipynb` to collect Amazon stock data
   - Execute `01 - Data exploration.ipynb` for comprehensive analysis
   - Data is stored in HDFS for distributed processing

### AWS Implementation
For AWS deployment and ML pipeline implementation, refer to the detailed roadmap in `todo.md`.

## Contributing

This project follows a structured development approach with clear separation between data processing, model development, and infrastructure management. Contributions should align with the three-stage implementation plan outlined above.

## License

This project is for educational and research purposes, demonstrating best practices in ML pipeline development and AWS cloud architecture.