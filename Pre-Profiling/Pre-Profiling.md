# Data Pre-Profiling

Here the anomalies of dataset were found out

```python
data.shape[0]-data.count()                                      #to find out the missing values
```
```python
100*(data.shape[0]-data.count())/data.shape[0]               #to find out the percentage of missing values
```
```python
data.duplicated().any()                                            #to find duplicate values
```
```python
#checking Tenure feature for presence of outliers
tenure_p_th = data.describe()['tenure']['75%'] + 1.5*(data.describe()['tenure']['75%'] - data.describe()['tenure']['25%'])  #finding positive threshold
tenure_n_th = data.describe()['tenure']['25%'] - 1.5*(data.describe()['tenure']['75%'] - data.describe()['tenure']['25%'])  #finding negative threshold
```
```python
data[(data['tenure']<tenure_n_th) | (data['tenure']>tenure_p_th)].shape[0]
```

## Observations:

- From the look and feel of data from the description part we can say that the outliers are less likely to be present and can be ignored if at all present. Let's check on some features for the same.
- There are 175 and 2 observations missing in gender and tenure features respectively in the dataset.

- Since the missing values are less than 0.18% of the data, it can be dropped.

- There are no duplicate values found in the data.

- Outliers are present but can be ignored in the context of data.

- Dataset has no inconsistent features present.

- No typos are present in the dataset.
