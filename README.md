# Predicting the Success of a Bank Marketing Campaign Using Machine Learning.
 Business Understanding\
 Data Understanding\
 Exploratory Data Analysis\
 Data Preparation\
 Model Building and Evaluation\
 Result


# BUSINESS UNDERSTANDING
This project describes the results of a bank’s marketing campaigns. The campaigns are based on direct phone calls, where the bank offers customers to open a term deposit. If the customer agrees to place a deposit after all these efforts, it is marked as ‘yes’; otherwise, it is marked as ‘no’. Based on this data, a decline in the bank’s revenue has been observed, and they want to know what measures they can take to address this situation.\
After the investigation, it turns out that the main reason is that customers no longer place deposits with the bank as frequently as before.


# DATA UNDERSTANDING
Data contains 41,188 rows and 20 columns. However, there are many duplicate rows in the dataset, which we handle first. After that, we are left with 39,404 rows and 20 columns. Our columns include both categorical and numeric values. The target column (y) has binary values (‘yes’ and ‘no’)

Sütunlarımız haqqında məlumatlar:\
	•	age: The customer’s age.\
	•	job: The customer’s profession or field of work.\
	•	marital: The customer’s marital status.\
	•	education: The customer’s education level.\
	•	default: Does the customer have unpaid credit?\
	•	housing: Does the customer have a housing loan?\
	•	loan: Does the customer have a personal loan?\
	•	contact: Type of communication with the customer.\
	•	month: The last month the customer was contacted.\
	•	day_of_week: The day of the week the customer was last contacted.\
	•	campaign: The number of contacts made with this customer during the campaign.\
	•	pdays: Number of days since the customer was last contacted in a previous campaign.\
	•	previous: The number of contacts made with this customer before the campaign.\
	•	poutcome: Outcome of the previous marketing campaign.\
	•	emp_var_rate: Employment variation rate - quarterly indicator.\
	•	cons_price_idx: Consumer price index - monthly indicator.\
	•	cons_conf_idx: Consumer confidence index - monthly indicator.\
	•	euribor_3m: 3-month Euribor rate - daily indicator.\
	•	nr_employed: Number of employees - quarterly indicator.\
	•	y: Has the customer subscribed to a term deposit?

Let’s look at and analyze the statistical values of our numeric columns.\ 
<img width="660" alt="Screenshot 2024-11-22 at 16 11 23" src="https://github.com/user-attachments/assets/6df465f9-93ea-4a06-b07e-619351599e6e">

1.	age:\
	•	Average Age (Mean): The average age of customers is approximately 40 years.\
	•	Minimum and Maximum Age (Min and Max): The age ranges from 17 to 98, showing that the bank serves customers across a wide age spectrum.\
	•	Standard Deviation (Std): A high standard deviation of 10.46 indicates significant variability in customer ages.\
2.	campaign:\
	•	Average Number of Campaigns (Mean): On average, each customer was part of 2.6 campaigns.\
	•	Maximum Campaigns (Max): One customer participated in 56 campaigns, indicating that some customers were contacted numerous times.\
	•	Standard Deviation (Std): A high standard deviation of 2.81 suggests substantial variation in the number of campaigns.\
3.	pdays:\
	•	Average Days (Mean): On average, 960 days have passed since the last campaign.\
	•	Minimum and Maximum Days (Min and Max): Some customers were contacted 0 days after the last campaign, while for others, it was 999 days (likely indicating no prior contact).\
	•	Standard Deviation (Std): A very high standard deviation of 190.87 reflects extreme variability.\
4.	previous:\
	•	Average Number of Contacts (Mean): On average, customers were contacted 0.18 times during previous campaigns, indicating rare repeat contacts.\
	•	Maximum Number of Contacts (Max): Some customers were contacted up to 7 times.\
5.	emp_var_rate (Employment Variation Rate):\
	•	Average Rate (Mean): The average employment variation rate is 0.064, indicating a slight positive change.\
	•	Minimum and Maximum Rate (Min and Max): The rate ranges from -3.4 to 1.4.\
6.	cons_price_idx (Consumer Price Index):\
	•	Average Index (Mean): The average index value is 93.58.\
	•	Minimum and Maximum Index (Min and Max): Values range from 92.20 to 94.77.\
	•	Standard Deviation (Std): A low standard deviation of 0.58 suggests relatively stable values.\
7.	cons_conf_idx (Consumer Confidence Index):\
	•	Average Index (Mean): The average index value is -40.50.\
	•	Minimum and Maximum Index (Min and Max): Values range from -50.8 to -26.9, reflecting overall low consumer confidence.\
8.	euribor_3m (3-Month Euribor Rate):\
	•	Average Rate (Mean): The average Euribor rate is 3.60.\
	•	Minimum and Maximum Rate (Min and Max): The rate varies between 0.63 and 5.04, showing variability in interbank rates.\
9.	nr_employed (Number of Employees):\
	•	Average Number (Mean): The average number of employees is 5165.98.\
	•	Minimum and Maximum Number (Min and Max): The number ranges from 4963 to 5228, indicating relatively stable quarterly employment levels.\

<img width="752" alt="Screenshot 2024-11-22 at 16 29 28" src="https://github.com/user-attachments/assets/edee324c-9f36-46da-a492-86ec985ee34f">

Key Features and Observations from the Matrix:\

1.	Emp_var_rate and Euribor_3m:\
	•	The strongest positive correlation (0.97) exists between these two variables.\
	•	This indicates a strong relationship between the employment variation rate and the 3-month Euribor rate. (Potential multicollinearity issue)\
2.	Nr_employed and Cons_price_idx:\
	•	There is also a high positive correlation (0.91) between the number of employees and the consumer price index.\
	•	This shows that these two variables are closely related.\
3.	Previous and Pdays:\
	•	A moderate negative correlation (-0.59) exists between the number of days since the customer was last contacted and the number of contacts made with the customer before the campaign.\
4.	High Positive Correlation:\
	•	There is a positive correlation of 0.78 between Cons_price_idx and Emp_var_rate.\
5.	Weak or Insignificant Correlations:\
	•	Weak or insignificant correlations are observed between age, campaign, pdays, and other variables.\

# EXPLORATORY DATA ANALYSIS

<img width="798" alt="Screenshot 2024-11-22 at 16 46 48" src="https://github.com/user-attachments/assets/207c2030-82b3-4874-98a5-079ef5475b3e">

<img width="877" alt="Screenshot 2024-11-22 at 16 57 35" src="https://github.com/user-attachments/assets/e876a981-7923-49f6-b41e-a6620385669a">

<img width="887" alt="Screenshot 2024-11-22 at 17 11 58" src="https://github.com/user-attachments/assets/a9edb646-3e16-43fb-aff4-5c30ca699ab6">

<img width="887" alt="Screenshot 2024-11-22 at 17 13 10" src="https://github.com/user-attachments/assets/23039007-b007-4171-8eed-4d8c78169a34">

<img width="887" alt="Screenshot 2024-11-22 at 17 14 46" src="https://github.com/user-attachments/assets/b9acc06a-b350-4248-9d33-44883ae2f88a">

<img width="887" alt="Screenshot 2024-11-22 at 17 15 53" src="https://github.com/user-attachments/assets/195df6af-78e9-4192-9083-c27559ef9f01">

# DATA PREPARATION

The charts show that many columns contain unknown values. There are several ways to handle missing data. One approach is to simply discard them; however, this would lead to a reduction in data, which does not align with our goal of building an accurate predictive model. Another approach is to intelligently infer the ‘unknown’ values from other variables. Columns with unknown values include: ‘job’, ‘marital’, ‘education’, ‘default’, ‘housing’, and ‘loan’.

For the ‘job’ and ‘education’ columns, my assumption is that ‘job’ is influenced by the level of ‘education’. Thus, based on a person’s education, we can predict the value for ‘job’.

By applying a smarter and more informed approach to managing ‘unknown’ values in this way, it is possible to minimize data loss while maintaining the accuracy of the predictive model.

<img width="614" alt="Screenshot 2024-11-22 at 17 17 35" src="https://github.com/user-attachments/assets/7f79e04e-19b4-4151-a2e6-17e623b2db3f">

Through this data, the relationships between the ‘education’ and ‘job’ columns can be seen more clearly. Based on these relationships, I use this table to estimate the unknown values in the ‘education’ and ‘job’ columns. For the unknown values in the ‘housing’ and ‘loan’ columns, I logically base them on the ‘job’ column. My assumption is that ‘housing’ should correspond proportionally to each ‘job’ category. Thus, I can determine the unknown values according to each job category.

<img width="905" alt="Screenshot 2024-11-22 at 17 18 09" src="https://github.com/user-attachments/assets/027d246e-9ad0-4df5-9c19-3bf2c6518476">

When examining outliers, I see that there are many outliers in the ‘age’ and ‘campaign’ columns. I am handling them.

<img width="905" alt="Screenshot 2024-11-22 at 17 18 49" src="https://github.com/user-attachments/assets/9bf78674-e215-4d66-8957-f3133290ab09">

Next, all missing values in the ‘pdays’ column were coded as ‘999’. This column actually contains many missing values. Further analysis showed that these missing values correspond to customers who had never been contacted before. To handle this, I replaced the ‘pdays’ column with numeric columns based on intervals such as ‘never contacted’, ‘contacted 5 or fewer days ago’, ‘contacted 6-15 days ago’, and so on.

Since our data contains many categorical columns, I used the get_dummies() function to create new variables based on these columns.

Later, I addressed the imbalance problem in our target column by generating additional samples using the oversampling method.

# MODEL BUILDING AND EVALUATION

6 different machine learning models were used. Each model was tested using different evaluation metrics, and results were compared to select the best model.

First, the dataset was split into features (X) and target (y). The target column ‘y_yes’ was chosen, representing whether the observation corresponds to a specific outcome or not.

**Train-Test Split:**\
The dataset was split into training and testing data with a ratio of 70%-30%. The stratify parameter was used to ensure balance in the target variable.\
**Scaling:**\
MinMaxScaler was applied to scale all feature values between 0 and 1.
**Models Used:**\
Six different machine learning models were implemented: Logistic Regression, Random Forest, Support Vector Machine, K-Nearest Neighbors, Decision Tree, and Naive Bayes.\
**Validation and Metrics:**\
Each model was tested using 5-fold cross-validation and evaluated using four different metrics: F1 Score, Accuracy, Precision, and Recall.

•	Logistic Regression: CV F1 Score: 0.71, CV Accuracy: 0.74\
•	Random Forest: CV F1 Score: 0.95, CV Accuracy: 0.95\
•	Support Vector Machine: CV F1 Score: 0.72, CV Accuracy: 0.76\
•	K-Nearest Neighbors: CV F1 Score: 0.84, CV Accuracy: 0.82\
•	Decision Tree: CV F1 Score: 0.93, CV Accuracy: 0.92\
•	Naive Bayes: CV F1 Score: 0.62, CV Accuracy: 0.69\

# RESULT
In this project, the Random Forest model showed the best performance on the given dataset. For future work, it may be beneficial to further optimize the model’s hyperparameters and collect more data.
