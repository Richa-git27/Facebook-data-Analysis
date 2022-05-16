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
[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/age-hist.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/age-hist.png)

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
[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/gender-gr.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/gender-gr.png)


### Observation

It shows that out of the total population 59.3% males are using facebook while 40.7% females are using facebook

------------


### Question

What is the percentage of male/female in most active age-group using facebook?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/agpe-pc.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/agpe-pc.png)

### Observation

Among the most active population, 63.5% are males while 36.5% are females

------------


### Question

What is the distribution of dob_month across the population?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/dob_mnt.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/dob_mnt.png)

### Observation

The date of birth month of January and October are found to be most common in the data. Lets explore it further

------------


### Question

What is the percentage of population having date of birth month as 'January' and 'October'?

```python
100*data[(data['dob_month'] == 10) | (data['dob_month'] == 1)].shape[0]/data['dob_month'].shape[0]
```
20.443000829741163

------------


### Question

What is the percentage of male and female in the population having date of birth month as 'January' or 'October'?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/gdr_domth.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/gdr_domth.png)

### Observation

Around 20% population is having date of birth month as January or October of which 62.9% are males while 37.1% are females.

------------


### Question

What is the distribution of dob_day across the population?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/dob_dy.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/dob_dy.png)

### Observation

Most common date of birth day is 1st or 10th day of a month.

------------


### Question

What is the percentage of population having date of birth day as 1st or 10th of a month?

```python
100*data[(data['dob_day'] == 1) | (data['dob_day'] == 10)].shape[0]/data['dob_day'].shape[0]
```

12.044401270920607

### Observation

12% of total population have their date of birth days as 1st and 10th of a month.

------------


### Question

What is the percentage of population having birth date as 1st or 10th of January or October?

```python
100*data[(data['dob_day'] == 1) | (data['dob_day'] == 10) & (data['dob_month'] == 10) | (data['dob_month'] == 1)].shape[0]/data.shape[0]
```

16.333758322708597

### Observation

16% of total population have date of birth days as 1st or 10th of January or October.

------------


### Question

What is the percentage of likes given by the population having date of birth day as 1st or 10th of January or October?

```python
100*data[(data['dob_day'] == 1) | (data['dob_day'] == 10) & (data['dob_month'] == 10) | (data['dob_month'] == 1)]['likes'].sum()/data['likes'].sum()
```

14.008574465184862

### Observation

14% of total likes are given by the population having date of birth day as 1st or 10th of January or October

------------

### Question

Which gender is giving/recieving more likes?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/gndr_likes.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/gndr_likes.png)

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/gndr_like_rec.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/gndr_like_rec.png)


### Observation

It shows that 67.9% females are giving likes whereas only 32.1% males are giving likes
As per the data the likes received by females is 71.8% whereas likes received by males is only 28.2%

------------


### Question

What is the genderwise distribution of mobile likes and web likes?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/mob_web_lik.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/mob_web_lik.png)

### Observation

The graph shows that mobile likes were higher as compared to web likes for both the genders
It shows that mobile app was used more for liking the posts as compared to web app
As compared to males, females use web app more likely.

------------


### Question

What is the genderwise distribution of likes recieved through mobile and web?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/mob_web_like_rec.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/mob_web_like_rec.png)

### Observation

It shows that the number of likes received on mobile were higher than on the likes recieved on web application following the same trend of more likes received by females than by males.

------------


### Question

What is the genderwise comparison of Friend Count and Friendships Initiated?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/frnd_ini_vs_count.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/frnd_ini_vs_count.png)

### Observation

More friendships were initiated by males as compared to females however females have higher friend count than males

------------


### Question

Which gender has spent longer time on facebook account?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/tenure_vs_age.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/tenure_vs_age.png)

### Observation

It shows that average tenure of females is higher than males

------------


### Question

Is there any relation between friend count and frienship initiated?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/scttr_frnd_ini_count.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/scttr_frnd_ini_count.png)

### Observation

Individuals having 0-1200 friend count are in majority as data point are much concentrated and they initiate lesser number of friend requests (0-1200)

------------


### Question

Is there any relation between friend count and likes given by individuals on various platforms?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/like_vs_count.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/like_vs_count.png)

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/moblike_vs_count.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/moblike_vs_count.png)

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/weblike_vs_count.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/weblike_vs_count.png)

### Observation

People with 0-1000 number of friend count tend to give more likes
Similar relation is observed between friend count vs mobile likes and web likes

### Question

What is the relation between tenure and friend count if any?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/tenure_count.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/tenure_count.png)

### Observation

We can observe that the maximum density lies between 300-400.
People with lesser tenure have more friend count

------------


### Question

What is the genderwise comparison of tenure vs friend count?

[![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/totaltenure_frndcount.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/EDA/totaltenure_frndcount.png)

### Observation

It shows that males have higher tenure than females but almost equal to little lesser friend count than females

------------
