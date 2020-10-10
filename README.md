# Predicting Client Churn

The aim of this project is to determine if the clients on the given database will make transactions again in the next two months. To achieve this, 6 tables will be used, containing data regarding transactions, demographics, behavior, finance, etc. The main platform to study is platform A (pa in the tables), which allows the user to save money, invest and pay for things or bills, etc; while also being closely related to platform B, which is a marketplace.

First, I am going to analyze the quality of the data in each table, fixing errors such as duplicates or null values (either removing or imputing them) and working with categorical features. Once fixed, we will build an input table to be used in the following sections.

Afterwards, I am going to do an exploratory data analysis to indentify key points that will help in achieving the main objective of this project. For this, I will check counts (independently and in relation to the response labels), variance, correlations, boxplots, distributions, and many more.

Lastly, I will start searching for a predictive model to determine if the client is going to churn or not. Three types of models will be used, while also trying to improve them by cross validating, parameter tuning and feature engineering.

Note: There's a data dictionary inside the notebook.
