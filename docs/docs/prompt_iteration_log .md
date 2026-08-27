# Prompt Engineering Technique Iteration Log

**Target Task (FL-01 Audit):** Automated baseline data validation and missing value audit script generation for search ranking datasets.

---

## 1. Naive Version (V0)

**Prompt:**
> Write a script to check missing values in my data.

**Output:**
```python
import pandas as pd
df = pd.read_csv("data.csv")
print(df.isnull().sum())
