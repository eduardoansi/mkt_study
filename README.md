# Marketing Campaign Analysis

This project aims to analyze data from a pilot campaign conducted with a small sample of the customer base of a food products shop.

After preprocessing the data, it was needed to suggest a customer classification model to improve the probability of achieving a profitable result when the complete campaign was executed.

### Files

- Mkt_Analysis.ipynb: complete notebook with the entire analysis and discussion
- Mkt_Campaign.twbx: Tableau file to be opened on the desktop application
- dashboard.png: Screenshot of the final dashboard

### Tools used

- Google Colab: as the Python IDE
- Pandas: library used to explore and preprocess the data
- SciKit-Learn: to perform the machine learning routine
- Tableau: to create the dashboard
- Inkscape: image editing

### Tasks

1. Explore and preprocess
2. Propose a classification model
3. Execute the model algorithm
4. Gather results and create a dashboard

#### 1. Explore and preprocess data

The dataset was relatively small but provided enough information to create a general customer profile, especially when analyzing how the features were correlated between themselves.

Before analyzing the correlation it was important to make sure all the variables had the correct data type in order to later run the models. To preprocess the data all the categorical features were transformed into binary columns, dates were used to calculate a period using days as a scale (for both Age and Period as Consumer), some outliers were removed as well as the rows that contained null Income values.

#### 2. Propose a classification model

Based on the initial analysis, it is noticeable that some features had a stronger correlation with the Response column, especially the variables about previous offers, quantity of products bought, income, among others. This suggests that a reasonable customer classification could be achieved it used a good methodology.

The goal was to maximize profit for when the campaign was executed on the entire database, so it was important to select the correct number of clusters that would provide a specific group of individuals more prone to aquiring the offer.

Clusterization using K-Means was the selected methodology, given that it is a good general purpose way of obtaining the needed result. As for the optimal number of clusters, the Elbow Method suggested 2 clusters, but when considering the company's objective - profitability - the best path was to iterate over several k values (where k is the number of clusters) to find a group with the highest profit rate. This calculation provided the optimal k being 8.

#### 3. Execute the model algorithm

The K-Means algorithm was executed again in order to gather all the needed information for visual display and future application on a larger dataset. A Snake Plot was created in order to visualize how all the features were weighted for each cluster, which served also as a confirmation that the optimal group had indeed the best probability of a favorable return.

#### 4. Gather results and create a dashboard

All the results and dataframes obtained during the analysis were exported in CSV files to be used with Tableau. A single dashboard was created with a general overview of the project and with the estimated financial results for a campaign launched considering a database of 500.000 customers.

For the interactive dashboard, click [here](https://public.tableau.com/profile/eduardo8266#!/vizhome/Mkt_Campaign/Dashboard1?publish=yes).

![image](https://github.com/eduardoansi/mkt_study/blob/master/dashboard.png)
