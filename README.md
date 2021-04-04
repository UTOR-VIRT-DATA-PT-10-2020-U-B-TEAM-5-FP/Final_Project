# **Cafe Chain Analysis**

## ***Segment 2 of the project :-***

## **Communication Protocol in the Team**

There is a robust communication protocol among the team members. We have already established the slack group, along with a TA. We continuously share ideas about the project and the issues faced by any team member and take help from our assigned TA. We also schedule zoom meetings on need basis outside the office hours.
## **Presentation**
The link of the presentation [can be reached here](https://1drv.ms/p/s!AkVDqlS3Ei2agpoFMxa9sUqR1cCPLA?e=dIhtIA)

In our project presentation, we have addressed the following:
### **Selection of Topic**
This is the analysis of a *Cafe chain* business which wants to understand its customers.

### **Reason Why We Selected This Topic**

Understanding of the customer base is one of the most important aspects of any business and same is true for a retail chain running coffee shops across the country. If the management has deep understanding of its business, they can take correct decisions to expand their business and make it profitable. The major reasons why we selected this data are:

* Real Life Example​
* Large Scale Business​
* Can be used for Machine Learning​
* Helpful for Data Visualizations​
* Data driven decision making in business​
* Understanding the Core Customer​

### **Description of The Data**

This is a real-life data collected by the management of "Our Cafe"" (Not the actual name for confidentiality reasons)- a  cafe chain business running their outlets across the country. It contains transaction‐level data from eight "Our Cafe" locations in a recent year. For each store, we have a random sample of daily transactions for 10 randomly selected days of each month. Each observation in the data represents a transaction and includes information on the specific items purchased and the prices and caloric content of those items. The data are limited to transactions that involve at most one drink and one food item — the vast majority of all transactions fall into this category. In addition,there is information about the demographic characteristics of the customer as well as the customer’s responses to three survey questions. 

Finally, there are features that indicate whether "Our Cafe" location at which the transaction took place, competes directly with a *medium size retail chain*, a *big retail chain* and an independent coffee shop. The precise variable definitions are below:

![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/cafe_data_features.png)

### **Questions to Answer**

There are many pertinent business questions a business might want to address to scale it's revenue and expansion. In the current analysis, we look forward to address the following questions :

* Popular Food / Drink Items  & Demand over the year​
* Identification of Customer Preferences (Taste/Price/  Calorie)​
* Customer Demographics​
* Core Customer of “Our Café”​
* Customer Spending Habits​
* Repeat Customers & Store Wise Distribution​
* Highest Revenue Stores​
* Reliability of Survey Answers & Actual Purchases​
* Prediction of repeat customers (Machine Learning)
* Recommendation of Food/ Drink items for the customer based upon their demographics and answers to 3 survey questions related to their preference of Taste/ Calories/ Price in making their purchase

### **Data Exploration phase**
In this phase, we are working on following:

* Data visualizations​
* Customer Demographics data​
* Stores and their order variations​
* Food and drink items​
* Store Performance​
* Repeat Customers & trends​
* Data set division as per machine learning model requirement​

Here are few images of Data exploration at this stage:
### **Customer Responses**
<img src='Resources/cust_preference.PNG'></img>

### **Popular Food/Drink Across All Shops**
<img src='Resources/food_items.PNG'></img>

### **Repeat Customer Orders**
<img src='Resources/repeat_cust_orders.PNG'></img>

## **Database Formation**
The project data has been stored in "SQLAlchemy" and being queried using PGAdmin and Flask.

We have initial dataset named: cafe_data.csv, which stores static data, as below:
![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/cafe_data_csv.png)

Dataset has been connected with **pgAdmin** in a Database named **cafe_db** with the help of following connection code in the Python scripts, for the interface:
![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/database_connection.png)

After having created tables customer_info, order_info and competitors from our original dataset cafe_data.csv and a complete table named cafe_original_data, in our database cafe_db,  to organize the data, we establish relationship between all the tables using the following snippet:

![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/relationship_between_tables.png)

Entity Relationship Diagram from the established relationship is as presented below:

![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/ERD.png)

Below is the code snippet to present the usage of SQL joins:

![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/joins.png)

## **Data Analysis phase**
In the analysis of the data, we have performed the following:
* checked statistical validity of our data
* checked for nulls and deleted as required
* checked datatypes and took out wrong datatype values and re-transformed datatypes
* dropped or excluded irrelevant columns
* encoded categorical data
* visualized our data
* binned data where appropriate
* checked columns for unique values
* split data into training and testing datasets
* created calculated conditions for our scripts for machine learning model
* supervised and unsupervised learning, dimensionality reduction
* rescaling data

to prepare machine learning model for recommendation Food & Drink Items as per their Demographics and Preferences
and identification & prediction for the Repeat Customer​ for "Our Cafe".

## **Machine Learning Model**
We are analyzing the dataset with different machine learning models to predict the following as explained briefly below:​​
### **Identifying & Predicting the Repeat Customer​**

#### **Description of preliminary data preprocessing:**

- We have a customer_info table with features which includes information about demographics of customers such as gender, age, cust_income. In addition, we have answers from the customers for three survey questions. These questions are about customer preferences towards taste, calories and price.We have order information of customers with calories and price.

![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/database_and_tables_in_postgresql.png)

- We joined customer_info and order_info tables after establishing connection with database cafe_db using SQL join for postgreSQL.

![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/preprocessing_repeat_cust.png)
#### **Description of preliminary feature engineering and preliminary feature selection, including their decision-making process:**
- From the joint table we have picked every column in cust_info table and total_spend features from orders_info table to define regular customer dataframe named reg_cust_df. By using these features, we have determined the number of visits by every customer based upon the cust_ID. 
- The rest of the features we are going to use to predict if the customer will be a regular customer
- We dropped the null values from the reg_cust_df dataframe which we made in the above step.
- We created some income ranges and used them as bins to use them in features instead of customers' specific income values.  
- In this table, we further filtered regular customers on the basis of a condition where every customer who has visited more than or equal to five items is considered as a regular customer
- Next, we created features by dropping cust_ID, cust_income and reg_cust column 
we selected regular customer as target 

![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/prelim_features_repeat_cust.png)
#### **Description of how data was split into training and testing sets**
- We used **sklearn** training_ test_split method to split our data into training and testing sets.	

	![](Resources/split_repeat_cust.png)
	
	- Used **Standard scaler** to scale our training and testing data by fitting the scaler on training data set and use that transformed training and testing datasets for our machine learning model

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/scaler_repeat_cust.png)
#### **Explanation of model choice, including limitations and benefits**
- To perform our machine learning predictions we used SVM,  EasyEnsemble, Neural Networks and Random Forest Classifier (RFC). Out of all these algorithms, RFC was able to give the predictions with most accuracy .

- Also, this model gave us respectable scores for classification .
	<img src='Resources/repeat_cust.PNG'></img>

- At the end we saved the model and the standard scaler to use it in the flask app for our dashboard. 

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/sav_model_repeat_cust.png)
	
 

### **Recommending Food & Drink Items as per their Demographics and Preferences​**

**A: Machine learning model for FOOD items clustering and recommendation prediction**
-	After establishing connection with our database ‘café_db’, where we already have all the tables from our **Database Formation** phase, as below :

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/database_and_tables_in_postgresql.png)

	we joined customer_info table and order_info table using SQL join query to select required data.

	From the resultant table , we dropped null values in **cust_ income** and 'food_type' columns, removed columns related to the **drink** and **total_spend**, as we don't need them in the model to predict the recommendation of food items. 

	
- #### **Description of preliminary feature engineering and preliminary feature selection, including their decision-making process:**

	- Created ranges for calories and price by specifying required conditions

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/preprocessing_food.png)

	- We used unsupervised machine learning model to cluster food items based upon the food_calories and food_price.
	
	Further, the **elbow curve** method was used to determine the option value for number of clusters for **KMeans algorithm**, which we came up as 3 clusters as below:

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/elbow_curve_food.png)
	
	Then we used KMeans algorithm with 3 clusters to predict the classes of the food items mentioned . We created a dataframe clustered _df using the clusters from KMeans algorithm to have all the unique food items with their classes and food_type.

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/food_items_cluster.png)
	
	- Created drink_class dataframe for sending it to a csv file to use it later in flask app.

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/food_items_to_csv.png)

	- Next we use the supervised machine learning to predict the class of the food items, for the customer based upon their gender, age, preference of taste, calories_importance, price_importance and the current month.

	-  Defined features and target for supervised machine learning

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/features_and_target_food_items.png)
- #### **Description of how data was split into training and testing sets**
	- We used **sklearn** training_ test_split method to split our data into training and testing sets.	

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/split_food.png)
	
	- Used **Standard scaler** to scale our training and testing data by fitting the scaler on training data set and use that transformed training and testing datasets for our machine learning model

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/scaler_food.png)
- #### **Explanation of model choice, including limitations and benefits:**

	- To perform our machine learning predictions we used SVM,  EasyEnsemble, Neural Networks and Random Forest Classifier (RFC). Out of all these algorithms, RFC was able to give the predictions with most accuracy .

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/rfc_food.png)

	- Also, this model gave us respectable scores for classification .
	<img src='Resources/food_cluster.PNG'></img>

	- At the end we saved the model and the standard scaler to use it in the flask app for our dashboard. 

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/sav_model_food.png)

**B: Machine learning model for DRINK items clustering and recommendation prediction**

- #### **Description of preliminary data preprocessing:**

	After establishing connection with our database ‘café_db’, where we already have all the tables from our **Database Formation** phase, as below :

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/database_and_tables_in_postgresql.png)

	we joined customer_info table and order_info table using SQL join query to select required data.

	From the resultant table , we dropped null values in **cust_ income** column, columns related to the **food** and **total_spend**, as we don't need them in the model to predict the recommendation of drink items. 
	Also we dropped the null values in the **drink_type** column .

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/preprocessing_drinks.png)
- #### **Description of preliminary feature engineering and preliminary feature selection, including their decision-making process:**

	- Replaced null values in the 'drink_milk' column with a space white space character 
	- Joined the 'drink_size', 'drink_type' and 'drink_milk' columns to create a new column 'Drink_Type'
	- Created ranges for calories and price by specifying required conditions

	- We used unsupervised machine learning model to cluster drink items based upon the drink_calories and drink_price.
	
	Further, the **elbow curve** method was used to determine the option value for number of clusters for **KMeans algorithm**, which we came up as 5 clusters as below:

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/elbow_curve_drinks.png)
	
	Then we used KMeans algorithm with 5 clusters to predict the classes of the drink items mentioned . We created a dataframe clustered _df using the clusters from KMeans algorithm to have all the unique drink items with their classes and Drink_Type.

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/drink_items_cluster.png)
	
	- Created drink_class dataframe for sending it to a csv file to use it later in flask app.

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/drink_items_to_csv.png)

	- Next we use the supervised machine learning to predict the class of the drink items, for the customer based upon their gender, age, preference of taste, calories, price and the current month.

	-  Defined features and target for supervised machine learning

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/features_and_target_drink_items.png)
- #### **Description of how data was split into training and testing sets**
	- We used **sklearn** training_ test_split method to split our data into training and testing sets.	

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/split_drinks.png)
	
	- Used **Standard scaler** to scale our training and testing data by fitting the scaler on training data set and use that transformed training and testing datasets for our machine learning model

	
	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/scaler_drinks.png)
- #### **Explanation of model choice, including limitations and benefits:**

	- To perform our machine learning predictions we used SVM,  EasyEnsemble, Neural Networks and Random Forest Classifier (RFC). Out of all these algorithms, RFC was able to give the predictions with most accuracy .

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/rfc_drinks.png)

	- Also, this model gave us respectable scores for classification .
	<img src='Resources/drink_cluster.PNG'></img>

	- At the end we saved the model and the standard scaler to use it in the flask app for our dashboard. 

	![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/sav_model_drinks.png)
## **Dashboard Preparation**
We are using *Tableau* for our data visualizations. The interactive elements on the story board are the filters we have used on all the pages of the story board. Using these filters, we can explore the trends in data for our questions as described above.

Below is a glimpse of our Tableau Storyboard.

### **Tableau Storyboard**

![](https://github.com/UTOR-VIRT-DATA-PT-10-2020-U-B-TEAM-5-FP/Final_Project/tree/kirti-segment-2/Tableau_storyboard_blueprint.png)

 To present our Machine Learning model, we have prepared and interactive *Web Application* (using Flask, HTML, Java) to display the options to the Cafe management to predict **Repeat Customers'** and the customers to **Recommend Food/Drink items** based upon their demographics and preferences.
### **Machine Learning Dashboard**

We are developing an interactive Web Application to help Management of the Cafe chain to identify a repeat customer. 

A glimpse of this app is as below:
<img src='Resources/machine_learning_model_dashboard.PNG'></img>



