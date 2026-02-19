# ML-Learning
## Numpy ---> use this github repo ---> ***https://github.com/AkarshVyas/Numpy-Youtube***

## 1️⃣ What is NumPy?

 - NumPy = Numerical Python

 - Why important for ML?

 - Fast numerical computation (C backend)

 - Works with arrays (ndarray)

 - Base of Pandas, Scikit-learn, TensorFlow

 - `import numpy as np`

---

## 2️⃣ Python List vs NumPy Array (Interview Question)
## Python List vs NumPy Array

| Python List | NumPy Array |
|-------------|------------|
| Slow | Fast |
| Mixed data types | Same data type |
| No vectorization | Supports vectorization |

Example:

np.array([1,2,3.5])
# Converts all to float

---

## 3️⃣ Creating Arrays (Must Know)

- `np.array([1,2,3])`
- `np.arange(1,10,2)`
- `np.zeros((3,4))`
- `np.ones((2,2))`
- `np.linspace(0,1,100)`

> 👉 `linspace` is very useful in ML and plotting.

---

## 4️⃣ Random (VERY IMPORTANT for ML)

### Used in:
- Weight initialization
- Train-test split
- Simulation

```python
np.random.rand(5)        # Uniform distribution (0 to 1)
np.random.randn(5)       # Normal distribution (mean = 0)
np.random.randint(1,10,5)
```

---

## 5️⃣ Array Properties (Interview Favorite)

```python
arr.shape
arr.size
arr.dtype
arr.ndim
```

Example: `(3,4)`
means 3 rows, 4 columns.

---

## 6️⃣ Axis Concept (EXTREMELY IMPORTANT 🔥)

```python
import numpy as np

np.sum(arr, axis=0)  # Column-wise
np.sum(arr, axis=1)  # Row-wise
```

👉 Axis Meaning

`axis = 0` → Downwards (operate along rows, gives column result)

`axis = 1` → Sideways (operate along columns, gives row result)

📌 Used In:

- Feature-wise mean
- Normalization
- ML preprocessing

---

## 7️⃣ Reshape (Very Common in ML)

```python
arr.reshape(5, 6)
📌 Rule:
rows × columns = total elements
```
🔥 Used before feeding data into ML models.

---

## 8️⃣ Indexing & Slicing

### 📌 1D Array

```python
arr[2]
arr[2:8:2]
```
### 📌 2D Array
```
arr[row, col]
arr[:, 2]      # Whole column
arr[2, :]      # Whole row
```
🔎 Important
: → Take everything

---

## 9️⃣ Boolean Indexing (VERY POWERFUL 🔥)

### 📌 Used For:

- Data filtering
- Feature selection

---

```python
arr[arr > 10]
arr[(arr > 10) & (arr < 20)]
```

⚠ Use & not and
---

## 🔟 View vs Copy (VERY IMPORTANT – INTERVIEW)

```python
slice = arr[2:5]
This is a view.
```

If you modify slice → original array changes 😱

✅ Safe Way
```
slice = arr[2:5].copy()
```
---

## 1️⃣1️⃣ Vectorization (Core of NumPy)

🚀 No loops needed

```python
a + b
a * b
a / b
a ** 2
```
All operations are element-wise

🔥 ML depends on this speed

---

## 1️⃣2️⃣ Broadcasting (VERY VERY IMPORTANT 🔥🔥)

```python
arr + 10
```
NumPy auto-adjusts shape

📌 Rule (Simple)
Shapes must be the same OR

One dimension must be 1

✅ Valid
```
(5, 5) + (5,)
```
❌ Invalid
```
(5, 5) + (4,)
```
📌 Used In
- Feature scaling

- Adding bias term

- Neural networks
---

## 1️⃣3️⃣ Matrix Multiplication (ML Core)

⚠ Most asked interview question

```
A * B        # element-wise
np.dot(A,B)  # matrix multiplication
A @ B        # modern way
```

Used in:

- Linear Regression

- Neural Networks

- Deep Learning

---

## 1️⃣4️⃣ Important Math Functions

```python
arr.min()
arr.max()
arr.mean()
arr.std()
arr.sum()

np.sqrt(arr)
np.exp(arr)
np.log(arr)
```

🔥 exp and log are heavily used in ML (Logistic Regression, Softmax)

---

## 1️⃣5️⃣ Transpose
A.T
`Converts row → column`

Very important in:

Linear algebra

Gradient calculations

---

## 1️⃣6️⃣ Stacking & Splitting (Basic Knowledge Enough)

### 📌 Stacking

```python
np.vstack((a, b))
np.hstack((a, b))
np.concatenate((a, b), axis=0)
```

📌 Splitting
```
np.hsplit(arr, 2)
np.vsplit(arr, 2)
```




## Pandas ---> use this repo ---> ***https://github.com/AkarshVyas/Pandas-Youtube***
`import pandas as pd`

## 1️⃣ Series (Basic Understanding Enough)
```sh
s = pd.Series([10,20,30])
```

Know:

- It is 1D

- Has index

- Rarely used alone in ML

👉 Just understand it. No deep focus needed.

## 2️⃣ DataFrame (VERY IMPORTANT)

This is the main thing.
```sh
df = pd.read_csv("data.csv")
df.head()
df.tail()
df.shape
df.columns
df.info()
df.describe()
```

🔥 Must know:

Rows = samples

Columns = features

## 3️⃣ Selecting Data (VERY IMPORTANT)
```sh
df["column"]          # Single column
df[["col1","col2"]]   # Multiple columns
df.iloc[0:5, 0:3]     # Position based
df.loc[0:5, "col1"]   # Label based
```

👉 `iloc` = index position
👉 `loc` = label name

Very common interview question.

## 4️⃣ Missing Data (EXTREMELY IMPORTANT 🔥)
```sh
df.isnull()
df.isnull().sum()
df.dropna()
df.fillna(0)
df.fillna(df.mean())
```

🔥 In ML, handling missing data is compulsory.

## 5️⃣ Filtering (VERY IMPORTANT)
```sh
df[df["age"] > 25]
df[(df["age"] > 25) & (df["salary"] > 50000)]
```

⚠ Use `&` not `and`

Used in:

- Data cleaning

- Feature filtering

## 6️⃣ GroupBy (IMPORTANT)
```sh
df.groupby("department").mean()
df.groupby("department")["salary"].sum()
```

Used in:

- Data analysis

- Feature engineering

## 7️⃣ Merging / Joining (IMPORTANT for real projects)
```sh
pd.merge(df1, df2, on="id")
```

Know:

- inner

- left

- right

Used when combining datasets.

## 8️⃣ Pivot Table (Basic Knowledge Enough)
```sh
pd.pivot_table(df, values="salary", index="department", aggfunc="mean")
```

Used in:

- Data summarization

## 9️⃣ Basic Operations (Must Know)
```sh
df["new_col"] = df["a"] + df["b"]
df.sort_values("salary")
df.drop("column", axis=1)
df.rename(columns={"old":"new"})
```




# Data Visualization
---> use this repo ---> ***https://github.com/AkarshVyas/Data-Visualization-Youtube***

There has 4 imp thing ---> histplot, boxplot, heatmap, countplot

# 1.Histplot ---> 
A histogram shows how a numerical variable is distributed by grouping values into ranges (bins).
```py
import seaborn as sns
import matplotlib.pyplot as plt

sns.histplot(df['age'])
plt.show()
```
🔥 Important Parameters ---> 

1️⃣ bins

Controls number of bars
```py
sns.histplot(df['age'], bins=20)
```

2️⃣ kde (Kernel Density Estimate)

Adds smooth curve
```py
sns.histplot(df['age'], kde=True)
```
3️⃣ stat

Controls what y-axis shows
```py
sns.histplot(df['age'], stat='count')      # default
sns.histplot(df['age'], stat='density')
sns.histplot(df['age'], stat='probability')
```
4️⃣ color
```py
sns.histplot(df['age'], color='red')
```
5️⃣ hue (Very Powerful)

Used to compare categories.
```py
sns.histplot(data=df, x='age', hue='gender', kde=True)
```
<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/1d1c2a7a-57d8-4351-b424-5ada88d291b6" />


# 2.Boxplot ---> 

🔹 Basic Syntax

1️⃣ Single numerical column
```py
import seaborn as sns
import matplotlib.pyplot as plt

sns.boxplot(x=df['salary'])
plt.show()
```
2️⃣ Categorical vs Numerical (Very Important)
```py
sns.boxplot(x='gender', y='salary', data=df)
```
🔥 Important Parameters

1️⃣ hue
```py
sns.boxplot(x='gender', y='salary', hue='department', data=df)
```
2️⃣ orient
```py
sns.boxplot(y=df['salary'])
```
3️⃣ showmeans
```py
sns.boxplot(x='salary', data=df, showmeans=True)
```
<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/e60c233f-d8f1-4c8c-9d93-07891276d31c" />


# 3.Countplot

A countplot shows the frequency (count) of each category in a categorical column.
