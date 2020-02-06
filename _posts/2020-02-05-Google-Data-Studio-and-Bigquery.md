---
title: "Google Data Studio: Dashboard using Bigquery"
categories:
  - Google Cloud
  - Google Data Studio
  - Bigquery
tags:
  - content
  - Google Cloud
  - Google Data Studio
  - Visualization
---

Creating the dashboard below by using the Google cloud tools.

<iframe width="600" height="450" src="https://datastudio.google.com/embed/reporting/4ad871f3-660e-490c-8f37-d49ac6a71a73/page/dyTDB" frameborder="0" style="border:0" allowfullscreen></iframe>

Steps to create the dashboard can be summarize in the following steps.

* Download the data set from a public site
* Prepare the data set information to upload
* Create a project in Google Cloud Console
* Create a Bigquery instance and upload the data set
* Create a Data Studio dashboard from Bigquery
* How to improve it ? 

### Download the data set from a Publica site 

1. First, We obtain the data for beer consumption from this [link](https://www.ttb.gov/resources/data-statistics/beer "Tax and Trade Bureau page")
2. Second, we will download use the [aggregated data - Beer Data by state from 2007 until 2018](https://www.ttb.gov/images/pdfs/statistics/aggregated/aggr-data-beer_2007-2018.xlsx "Aggregated excel file")


### Prepare the data set information to upload

1. We will use python to download the file and organize the data.
```python
import pandas as pd
import numpy as np
import datetime as dt

linkfile= 'https://www.ttb.gov/images/pdfs/statistics/aggregated/aggr-data-beer_2007-2018.xlsx'
for i in range(3):
    print('iteration number = ',i+1)
    data = pd.read_excel('C:/Users/David/Downloads/aggr_beer_2007_2018.xlsx',sheet_name = i,header=0,nrows=51)
    data = pd.read_excel(linkfile,sheet_name=i,header=0,skiprows=7,usecols = list(range(13)))
    data.drop(datsa.index[0],inplace = True)
    if i >= 1:
        dataMelt = data.melt(id_vars='State',var_name='Year')
    else:
        dataMelt = data.melt(id_vars='STATE',var_name='Year')
    filename = 'C:/Users/David/Downloads/Python_aggr_beer_2007_2018_table_'+ str(i) +'.csv'
    dataMelt.to_csv(filename)
```
2. ordered item 
   * **unordered**
   * **unordered** 
     * unordered item
     * unordered item
3. ordered item
4. ordered item

### Unordered -- Ordered -- Unordered

* unordered item
* unordered item 
  1. ordered
  2. ordered 
     * unordered item
     * unordered item
* unordered item
* unordered item

### Unordered -- Unordered -- Ordered

* unordered item
* unordered item 
  * unordered
  * unordered 
    1. **ordered item**
    2. **ordered item**
* unordered item
* unordered item

### Task Lists

- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request