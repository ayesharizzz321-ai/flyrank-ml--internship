# Prompt Iteration Log: Automated Data Profiling & Cleaning Script Generation

## Task Overview
* **Goal:** Generate a production-ready Python script using Pandas/NumPy to audit, clean, and profile an incoming tabular dataset.
* **Target Audience:** Data Science / Engineering team.

---

## Iteration 0 (v0): Baseline (Naive Prompt)
* **Technique:** None (Naive Baseline)
* **Prompt:**
  ```text
  Write a python script to clean missing values and outliers in a dataframe.
You are a Senior Data Engineer specializing in robust ETL pipelines and defensive programming in Python. 
Write a python script to clean missing values and outliers in a dataframe.
You are a Senior Data Engineer specializing in robust ETL pipelines and defensive programming in Python. 

We are building an automated ingestion pipeline for noisy real-world tabular data. Data arrives with mixed types, missing values, and numerical extreme values. We need a modular cleaning script so downstream ML models do not fail on bad inputs.

Write a Python script to clean missing values and outliers in a dataframe.
You are a Senior Data Engineer specializing in robust ETL pipelines. 
We are building an automated ingestion pipeline for noisy real-world tabular data.

Follow this specific function signature and docstring pattern for all cleaning functions:

Example Input/Output Format:
```python
def remove_outliers_iqr(df: pd.DataFrame, column: str, factor: float = 1.5) -> pd.DataFrame:
    """Removes outliers from a numerical column using the IQR method.

    Returns modified DataFrame and logs dropped count.
    """You are a Senior Data Engineer specializing in robust ETL pipelines.
Write a modular Python script for data cleaning.

Structure your response into exactly three distinct sections:
1. **Executive Summary**: Brief explanation of handling strategy (2 sentences max).
2. **Python Implementation**: Production-grade module with type hints, docstrings, and modular functions.
3. **Usage Example**: A self-contained runnable example using synthetic Pandas data.
4.You are a Senior Data Engineer specializing in robust ETL pipelines.
Write a modular Python script for data cleaning.
You are a Senior Data Engineer. You need to create a production-grade data cleaning module.

Think step-by-step before writing code:
Step 1: Analyze schema types (separate numeric vs. categorical features).
Step 2: Define missing value strategies (impute numeric with median, categorical with mode, flag missingness).
Step 3: Define IQR-based outlier capping (clip values rather than drop rows to preserve sample size).
Step 4: Output execution summary metrics (return cleaned DataFrame + execution dictionary).

Now, execute this step-by-step logic and write the full Python script with a runnable demonstration.
Structure your response into exactly three distinct sections:
1. **Executive Summary**: Brief explanation of handling strategy (2 sentences max).
2. **Python Implementation**: Production-grade module with type hints, docstrings, and modular functions.
3. **Usage Example**: A self-contained runnable example using synthetic Pandas data.
4.
    # implementation
    return df_clean
