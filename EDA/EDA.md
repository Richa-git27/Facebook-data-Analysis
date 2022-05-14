# EDA

Here we asked and solved some questions pertaining to our defined problem and on the basis of observations draw further conclusions

### Question

Which age-group is using facebook the most?

```python
#To find out the frequency of most using age-group we will plot a histogram on age feature

figure = plt.figure(figsize=[15, 7])

b = 10
bins = range(0,116, int(115/b))
data['age'].plot.hist(bins=bins, color='brown')

plt.xticks(ticks=bins, size=10, rotation=90)
plt.yticks(ticks=np.arange(0, 35001, 5000), size=7)
plt.xlabel(xlabel='age', size=14)
plt.ylabel(ylabel='Frequency', size=14)
plt.title(label='Age-wise Distribution of Facebook users', size=16)
plt.show()

```
### Observation

- Facebook is being used by people ranging from 13 to 113 however the most actively using population belongs to age group 11-33 and there is a sharp decline noticed in usage post 33 years of age followed by declining trend and a little rise between 99-110


------------

### Question

What is the percentage of most active age group out of total population?

```python
100*data[(data['age'] >= 11) & (data['age'] <= 33)].shape[0]/data['age'].shape[0]
```
59.2101268896849

### Observation

About 59% of total active population falls in the age-group of 11-33 years

------------

### Question

Which gender among the total population is using facebook more?

```python
#To find out the most common gender using facebook we will perform value counts on gender feature and plot a donut chart

figure = plt.figure(figsize=[10, 10])

data['gender'].value_counts().plot(kind='pie',autopct='%3.1f%%',explode=np.ones(2)/10,wedgeprops=dict(width=0.15),fontsize=12,shadow=True,cmap='inferno',label='')

plt.ylabel(ylabel='Gender', size=14)
plt.title(label='Donut Plot showing the usage of facebook by each Gender', size=18)
plt.show()
```
