# Predicting Client Churn

The aim of this project is to determine if the clients on the given database will make transactions again in the next two months. To achieve this, 6 tables will be used, containing data regarding transactions, demographics, behavior, finance, etc. The main platform to study is platform A (pa in the tables), which allows the user to save money, invest and pay for things or bills, etc; while also being closely related to platform B, which is a marketplace.

First, I am going to analyze the quality of the data in each table, fixing errors such as duplicates or null values (either removing or imputing them) and working with categorical features. Once fixed, we will build an input table to be used in the following sections.

Afterwards, I am going to do an exploratory data analysis to indentify key points that will help in achieving the main objective of this project. For this, I will check counts (independently and in relation to the response labels), variance, correlations, boxplots, distributions, and many more.

Lastly, I will start searching for a predictive model to determine if the client is going to churn or not. Three types of models will be used, while also trying to improve them by cross validating, parameter tuning and feature engineering.

So, before we start, here is the data dictionary regarding the tables.
   1. ACCOUNT_MONEY: Contains data about the amount of cash in the account and if the user is investing.
           a. cus_id: Customer ID.
           b. money_1: Amount of cash in the previous month (-1).
           c. money_2: Amount of cash in the previous two months (-2).
           d. investment: If the user is eligible to invest, is investing or not.
   2. ACTIVE_USER: Contains data about the visits to each app (for platforms A and B).
           a. cus_id: Customer ID.
           b. pa_n: Amounts of visits per month for platform A on the previous N month (either 1, 2 or 3).
           c. pb_n: Amounts of visits per month for platform B on the previous N month (either 1, 2 or 3).
           d. last_login_pa: Date of the last login for platform A in each month.
           e. last_login_pa: Date of the last login for platform B in each month.
   3. DEMOGRAPHICS: Contains demographic data about the users.
           a. cus_id: Customer ID.
           b. city.
           c. gender.
           d. age.
           e. pay_type: Type of payment they have access to (Credit/Debit/etc).
           f. province.
   4. EVALUATE: Contains the labels for each user. Used to test the models.
           a. cus_id: Customer ID.
           b. churn: if the user will stop using the platform in the next two months or not.
   5. MARKETPLACE_DATA: Summary of each users' transaction records on platform B on the last 6 months.
           a. cus_id: Customer ID.
           b. spent_pb: Amount of cash spent.
           c. last_date_pb: Date of the last purchase on the platform.
           d. frequency_pb: Amount of days each user made a purchase.
   6. PAYMENTS: Transactional data on platform A for each user.
           a. cus_id: Customer ID.
           b. date: Date of the transaction.
           c. cus_id_seller: Seller ID.
           d. spent_pa: Amount spent on the transaction.
           e. segment: Transaction type.
           f. discount_pa: Discount the buyer received on the transaction.
