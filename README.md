


## 1. Tools & Libraries

* Google Colab / Jupyter Notebook
* Python Libraries:

  * pandas
  * numpy

---

## 2. Import Libraries

```python
import pandas as pd
import numpy as np
```

---

## 3. Load the Dataset

```python
df = pd.read_csv('student_data.csv')
```

---

## 4. Initial Data Exploration

```python
df.head()
```

```python
df.info()
```

Purpose:

* Understand column names
* Check data types
* Identify missing values

---

## 5. Identify Missing Values

```python
df.isnull().sum()
```

Observation:

* Missing values found in selected columns
* Cleaning required before analysis

---

## 6. Handle Missing Values

### Numerical Columns – Fill with Mean

```python
df['math_score'] = df['math_score'].fillna(df['math_score'].mean())
```

### Categorical Columns – Fill with Mode

```python
df['gender'] = df['gender'].fillna(df['gender'].mode()[0])
```

Reason:

* Mean keeps numeric distribution stable
* Mode preserves most frequent category

---

## 7. Remove Duplicate Records

```python
before = df.shape[0]
df = df.drop_duplicates()
after = df.shape[0]
print('Duplicates removed:', before - after)
```

---

## 8. Data Type Conversion

```python
df['reading_score'] = df['reading_score'].astype(int)
```

Why?

* Correct datatypes ensure accurate calculations and analysis

---

## 9. Feature Engineering (Create New Column)

### Average Score Column

```python
df['average_score'] = (df['math_score'] + df['reading_score'] + df['writing_score']) / 3
```

---

## 10. Save Cleaned Dataset

```python
df.to_csv('cleaned_data.csv', index=False)
```

---

## 11. Final Outcome

* Dataset cleaned and ready for analysis
* Manual Excel work replaced using Python
* Scalable and reproducible cleaning workflow created

