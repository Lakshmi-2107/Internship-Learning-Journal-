# Insights

## Fraud & Transaction Patterns

* Fraud vs non-fraud disputes can be analyzed across regions using pivot tables.
* No strong geographical pattern may indicate:

  * Randomized dataset
  * Lack of meaningful segmentation

## Time-Based Trends

* Transaction approvals analyzed by hour/day showed:

  * No consistent pattern
  * Suggests randomness in dataset

## Statistical Relationships

* Correlation analysis helps identify:

  * Strong relationships (close to +1 or -1)
  * Weak relationships (~0)

Example:

* Cases vs Deaths → Strong correlation (~0.84)
* Vaccination vs Deaths → Weak correlation (~0.23)

## Regression Insights

* Regression models help quantify relationships:

  * R² ~ 0.66 → 66% variance explained
* Key findings:

  * Positive coefficient → Direct relationship
  * Negative coefficient → Inverse relationship
* Always validate using **p-values (< 0.05)**

## Forecasting Observations

* Linear forecasting works well for:

  * Simple trends
* Seasonal forecasting (ETS) is better for:

  * Cyclical data

## Outlier Impact

* Outliers can:

  * Skew results
  * Indicate errors OR valuable insights
* Decision:

  * Remove if error
  * Retain if meaningful

## Geospatial Insights

* Store location analysis shows:

  * Customer proximity is critical
  * Density impacts competition
* Example:

  * High store density → saturation
  * Sparse areas → opportunity

## Performance Insights

* DuckDB vs Pandas:

  * DuckDB is significantly faster (~20x)
  * More memory efficient
  * Works directly on disk

## Key Takeaway

Insights must always be validated. Correlation does not imply causation, and patterns in synthetic data may not reflect real-world behavior.
