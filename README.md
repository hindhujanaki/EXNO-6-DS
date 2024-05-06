# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 
## Line Plot using Seaborn
```python
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt

df = sns.load_dataset("tips")
df
```
![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/a22d6ac3-edf8-4252-82d1-61d21156cb46)


```python
sns.lineplot(x="total_bill", y= "tip", data = df, hue = "sex", linestyle="solid", legend= "auto" )
```
![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/f4ce6ab6-c4bb-4283-b22d-ce2fcb35e11b)


## Bar Chart using Seaborn
```python
tips = sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()

plt.figure(figsize=(8,6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label = 'Total Bill', color="sienna")
p2 = plt.bar(avg_tip.index, avg_tip,bottom = avg_total_bill, label = 'Tip',color="coral")

plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()

```
![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/f97fb114-0278-40af-9523-b8dd03d7448c)


```python
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()

p1 = plt.bar(avg_total_bill.index, avg_total_bill, label = 'Total Bill', width=0.4,color='wheat')
p2 = plt.bar(avg_tip.index, avg_tip,bottom = avg_total_bill, label = 'Tip', width=0.4, color='lightsalmon')

plt.xlabel('Time of the day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```
![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/dfcb508d-8c5a-47c3-acad-d604620f40cc)


```python
dt = sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill',hue='sex',data=dt, palette='rainbow')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Totak Bill by Day and Gender')
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/0e46dbb6-a9a6-49cf-aca3-e37100651226)


## Scatterplot using Seaborn
```python
import seaborn as sns
tip=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip',hue='sex',data=tips)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/bf652966-88d2-4cae-8e8f-19662c5ef2e9)


## Histogram using Seaborn
```python
import numpy as np
np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)

sns.histplot(data=marks, bins=10, kde=True, stat='count', cumulative=False, multiple='stack',color='crimson', element='bars', shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Students Marks')

```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/5dad43f6-6fef-4bdb-86a0-f2fd840c08e4)


## Box Plot using Seaborn
```python
tips = sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/ebc96169-6b4e-4c69-8023-b4638cab6136)


## Violin Plot using Seaborn
```python
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")

plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of total bill by the day and smoker status")
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/e5c489d1-b8e0-4a79-9c8b-2a507218973c)


```python
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day', y='tip', data=tip, palette="Set2")
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/5b37cd69-2f3f-450f-8f66-a5589014d3f2)


```python
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='tip', y='day', data=tip, palette="Set3")
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/32eaa06a-42c4-4731-af42-d36ec67fdb70)


## KDE Plot
```python
sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='fill', linewidth=3, palette='Set2', alpha=0.8)
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/d2a77aa8-ba0b-48a7-b924-f05853165826)


```python
sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='layer', linewidth=3, palette='Set2', alpha=0.8)
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/b23c2a15-4d8b-4a11-9699-55baf85fae5c)


```python
sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='stack', linewidth=3, palette='Set2', alpha=0.8)
```

![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/7d0b65c4-31fe-475a-9d08-d8e39d20793e)

## Heat Map using Seaborn
```python
import numpy as np
data=np.random.randint(low=1, high=100, size=(10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/hindhujanaki/EXNO-6-DS/assets/148514666/9aa5e388-aec4-4beb-a889-40dbeda96ba2)



# Result:
Thus, Data Visualization using seaborn python library for the given datas has been performed.

