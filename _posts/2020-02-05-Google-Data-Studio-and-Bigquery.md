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

## 1. Download the data set from a Publica site 

* First, We obtain the data for beer consumption from this [link](https://www.ttb.gov/resources/data-statistics/beer "Tax and Trade Bureau page")
* Second, we will download use the [aggregated data - Beer Data by state from 2007 until 2018](https://www.ttb.gov/images/pdfs/statistics/aggregated/aggr-data-beer_2007-2018.xlsx "Aggregated excel file")


## 2. Prepare the data set information to upload

* We will use python to download the file and organize the data. 
Here is the code to create 3 CSV files to upload the data in BigQuery

```python
import pandas as pd
import numpy as np
import datetime as dt

filenamepath = 'C:/Users/David/Downloads/Python_aggr_beer_2007_2018_table_'
linkfile= 'https://www.ttb.gov/images/pdfs/statistics/aggregated/aggr-data-beer_2007-2018.xlsx'
for i in range(3):
    data = pd.read_excel(linkfile,sheet_name=i,header=0,skiprows=7,usecols = list(range(13)),nrows=5)
    data.drop(datsa.index[0],inplace = True)
    if i >= 1:
        dataMelt = data.melt(id_vars='State',var_name='Year')
    else:
        dataMelt = data.melt(id_vars='STATE',var_name='Year')
    filename = filenamepath + str(i) +'.csv'
    dataMelt.to_csv(filename)
```

## 2. Create a project in Google Cloud Console

* We will go and create a project in google cloud. If you don't have an account you can go to this [link](https://www.youtube.com/watch?v=P2ADJdk5mYo "The Google Cloud Platform Free Trial and Free Tier - Don't confuse them")   

* We will go to google cloud account in this [link](   )
![Test Image 1]()
![Screenshot](https://drive.google.com/file/d/1zZbIAy5MSTdF8QHKwsEsWMO0bD7DojnF/view)
<img src="https://drive.google.com/file/d/0B6wwyazyzml-OGQ3VUo0Z2thdmc/view">


## 3. Create a Bigquery instance and upload the data set
## 4. Create a Data Studio dashboard from Bigquery
## 5. How to improve it ?

### Task Lists

- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request