# Exploratory Data Analysis (EDA)

## Overview

Exploratory Data Analysis (EDA) is the first and most critical step in any data science workflow. It helps in understanding the structure, patterns, and anomalies in the dataset before applying advanced techniques.

## Data Loading

* Data is loaded using **Pandas**, typically from efficient formats like **Parquet**.
* Parquet is preferred over CSV/Excel due to:

  * Faster read/write speeds
  * Better compression
  * Columnar storage

```python
import pandas as pd
df = pd.read_parquet("data.parquet")
```

## Initial Exploration

* Preview dataset using:

```python
df.head()
df.columns
df.info()
```

* Understand:

  * Data types
  * Missing values
  * Feature distribution

## Fraud Pattern Analysis

* Use **pivot tables** to analyze disputes:

```python
pd.pivot_table(df, values='transaction_id', index='region', columns='fraud_flag', aggfunc='count')
```

* Helps identify:

  * Fraud vs Non-Fraud distribution
  * Regional differences

## Statistical Analysis

* Analyze relationships between variables:

  * Transaction amount vs approval
  * Domestic vs cross-border impact
* Use correlation:

```python
df.corr()
```

## Time Series Analysis

* Extract time features:

```python
df['hour'] = df['timestamp'].dt.hour
df['date'] = df['timestamp'].dt.date
```

* Visualize patterns:

  * Heatmaps
  * Hourly trends

## Outlier Detection

* Use IQR method:

  * Q1 = 25th percentile
  * Q3 = 75th percentile
  * IQR = Q3 - Q1

* Bounds:

  * Lower = Q1 - 1.5 * IQR
  * Upper = Q3 + 1.5 * IQR

* Outliers:

```python
df[(df['value'] < lower) | (df['value'] > upper)]
```

## Visualization

* Box plots for outliers
* Heatmaps for time patterns
* Scatter plots for relationships

## Key Takeaway

EDA helps uncover hidden patterns, validate assumptions, and prepare data for modeling. However, always verify whether patterns are real or artifacts of synthetic/random data.
