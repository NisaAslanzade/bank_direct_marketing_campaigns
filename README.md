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
	3.	pdays:
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
	•	Minimum and Maximum Number (Min and Max): The number ranges from 4963 to 5228, indicating relatively stable quarterly employment levels.
