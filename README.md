# Final_Project

## Coffee Chain Analysis- Team 5

### Selection of Topic

This is the analysis of a Coffee chain business which wants to understand it's customers and their preferences.

### Reason Why We Selected This Topic

Understanding of the customer base is one of the most important aspects of any business and same is true for a retail chain running coffee shops across the country. If the management has deep understanding of its business, they can take correct decisions to expand their business and make it profitable. For a retail chain, questions like where to open their next shop or how to improve their inventory turnover are paramount for their success. By using Data analytic tools, we will try to help the management to overcome these challenges.

## Description of The Data

This is a real-life data collected by the management of "Our Cafe"" (Not the actual name for confidentiality reasons)- a coffee chain business running their outlets across the country. It contains transaction‐level data from eight "Our Cafe" locations in a recent year. For each store, we have a random sample of daily transactions for 10 randomly selected days of each month. Each observation in the data represents a transaction and includes information on the specific items purchased and the prices and caloric content of those items. The data are limited to transactions that involve at most one drink and one food item—the vast majority of all transactions fall into this category. In addition, there is information about the demographic characteristics of the customer as well as the customer’s responses to three survey questions. Finally, there are variables that indicate whether "Our Cafe" location at which the transaction took place competes directly with a medium size retail chain, a big retail chain or an independent coffee shop. The precise variable definitions are below:

### Variable Definition

    Cust_ID A unique customer identifier

    Store_ID A unique store identifier

    Transaction A unique transaction identifier

    Day The day of the month on which the transaction took place

    Month The month in which the transaction took place

    Food A dummy variable that equals 1 if the transaction involved a food purchase

    Drink A dummy variable that equals 1 if the transaction involved a drink purchase

    Drink_Type The specific type of drink purchased (e.g.: Latte, Cappuccino, Drip Coffee, etc... )The variable is missing for transactions that did not involve a drink purchase.

    Drink_Size The size of drink purchased (small, medium, large). The variable is missing for transactions that did not involve a drink purchase.

    Drink_Milk The type of milk in the drink if applicable (skim, 2%). The variable is missing for drink types that cannot customize the milk when ordered and for transactions that did not involve a drink purchase.

    Drink_Price The price paid for the drink. The variable is missing for transactions that did not involve a drink purchase.

    Drink_Calories The number of calories in the drink. The variable is missing for transactions that did not involve a drink purchase.

    Food_Type The specific type of food item purchased (e.g.: . The variable is missing for transactions that did not involve a food purchase.

    Food_Price The price paid for the food item. The variable is missing for transactions that did not involve a food purchase.

    Food_Calories The number of calories in the food item. The variable is missing for transactions that did not involve a food purchase.

    Total_Spend The total amount paid for the items purchased

    Cust_Gender The customer’s gender: 0 indicates female; 1 indicates male

    Cust_Age The customer’s age in years

    Cust_Income The customer’s annual income

    Ans_q1_Taste The customer’s stated answer to the following question: On a scale of 1 to 5, how important is taste when you choose what items to purchase? 1’ indicates “not important” and 5’ indicates “very important”.

    Ans_q2_Price The customer’s stated answer to the following question: On a scale of 1 to 5, how important is price when you choose what items to purchase? 1’ indicates “not important” and 5’ indicates “very important”.

    Ans_q3_Calories The customer’s stated answer to the following question: On a scale of 1 to 5, how important is caloric content when you choose what items to purchase? 1’ indicates “not important” and 5’ indicates “very important”.

    Comp_med A dummy variable that equals 1 if the store is within 0.5 km of a medium competitor

    Comp_big A dummy variable that equals 1 if the store is within 0.5 km of a big competitor store

    Comp_Indep A dummy variable that equals 1 if the store is within 0.5 km of an independent coffeehouse (single store owner)

### Questions We Hope To Answer

There are many pertinent business questions we want to address and hope that we will be able to answer them. Currently we have addressed <b>the following question:</b>

    * Helping the "Our Cafe" management to understand Drink or Food preferences

    and Some other questions we will be trying to answer are:

    * What are the most popular items in their menu (Helps inventory management)?

    * Whether the demand of these items remain steady for whole year?

    * What are the demographics of their customers (Age, Gender, Income etc)?

    * Can we identify whether their customers are price or taste or calorie conscious?

    * What is the distribution of transactions and revenues across customers of different income levels?

    * What is the relationship of customers' answers to the survey questions and the actual purchases they made?

    * Can we identify the core customer of this coffee chain (Age/Gender/Income/Preference etc) so that the management can correctly target the right people in their upcoming media campaign?

    * Can we help the management in selection of retail locations of their upcoming shops (high end streets/educational hubs/low end streets)?

    * Can we identify the core competitor (Medium sized chain/ Big chain/ Independent coffee shops)

### Communication Protocol in the Team

There is a robust communication protocol among the team members. We have already established the slack group and continuously share ideas about the project and the issues faced by any member and take help from our assigned TA. We also schedule zoom meetings on need basis outside the office hours. 