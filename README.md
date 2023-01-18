# crowdfunding-ETL
Perform ETL process for Independent Funding
## Overview

Independent Funding is a crowdfunding platform for funding independent projects or ventures.
Independent Funding has been growing, so now it needs to move all their accessible data from one large Excel file onto a PostgreSQL database. Therefore, our task was to do the following:
- Extracting and transforming the data from a large Excel files into CSV files.
- Creating a PostgreSQL database and tables by using an ERD.
- Loading the CSV files into the database.
- Performing SQL queries to generate reports for stakeholders.

### Aim 
The aim of this project is to help the company build a database with SQL. This way, the analytics team will be able to perform analysis and create reports for company stakeholders as well as individuals who donate to projects..

## Resources 
- Data Source: crowdfunding.xlsx - backer_info.csv 
- Software: Python 3.7.13, Jupyter Notebook, SQL, PostgreSQL, pgAdmin 4

## Analysis of Data and Results 
The ETL process for Independent Funding is divided into the following steps:

### Step 1: Extract the Data 
Using Python and Pandas we have extracted:
-  4 CSV files from ```crowdfunding.xlsx``` file. 
The code used is saved as ```Extract-Transform_final_code.ipynb``` (https://github.com/akhue02/crowdfunding-ETL/blob/main/Crowdfunding-ETL/Extract-Transform_final_code.ipynb)
- 1 CSV file from ```backer_info.csv```
The code used is saved as ```Extract-Transform_starter_code.ipynb``` (https://github.com/akhue02/crowdfunding-ETL/blob/main/Crowdfunding-ETL/Extract-Transform_final_code.ipynb)
To extract these CSV files 2 methods were used:
- Python dictionary method. 
- Regular expression method. 


### Step 2: Transform and Clean Data 

Using Python, Pandas, and data cleaning strategies, we have transformed the data via formatting, splitting, converting data types, and restructuring to create DataFrames that can be loaded into a postgreSQL database as a CSV file.

When finishing this step, we have 5 CSV cleaned files saved as:
- contacts.csv 
- category.csv
- subcategory.csv
- capaign.csv 
- backers.csv 

Codes used in this step is also saved as ```Crowdfunding-ETL.ipynb``` (https://github.com/akhue02/crowdfunding-ETL/blob/main/Crowdfunding-ETL/Crowdfunding-ETL.ipynb)
### Step 3: Create an ERD and Table Schema, and Load Data

In order to load the cleaned datasets as CSV files into an SQL database we started by creating an Entity Relationship Diagram (ERD) using Quick DBD website (https://www.quickdatabasediagrams.com).

When the database schema is complete, we have saved the ERD as ```crowdfunding_db_relationships.png``` (See Fig.1) and we have saved the database schema as a PostgreSQL file named ```crowdfunding_db_schema.sql``` (https://github.com/akhue02/crowdfunding-ETL/blob/main/Crowdfunding-ETL/crowdfunding_db_schema.sql)

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://github.com/akhue02/crowdfunding-ETL/blob/main/Crowdfunding-ETL/crowdfunding_db_schema.png">
</p>
<p align = "center">
Figure 1 - Crowfunding Entity Relationship Diagram (ERD) 
</p>

The next step was to pass and run the PostgreSQL file into PgAdmin query editor in order to create the tables. Finally, we have uploaded the CSV cleaned files into these tables. 

### Step 4: SQL Analysis 

After creating the crowdfunding database, it has become easy to to perform analysis and create reports for company stakeholders. Therefore, we have created the following queries: 

- **Query 1 and 2:** </br>
These SQL queries were used to find the "backer_counts" in descending order for each "cf_id" using the "Campaign" table and the "Backers" table consecutively. </br>


- **Query 3:** </br> 
This query was written to help the company send an email for each contact of every live campaign and inform them how much of the goal remains. To help them do so we have created the "email_contacts_remaining_goal_amount" table saved as ```email_contacts_remaining_goal_amount.csv``` https://github.com/akhue02/crowdfunding-ETL/blob/main/Crowdfunding-ETL/email_contacts_remaining_goal_amount.csv

- **Query 4:** </br> 
This query was written to help the company send an email to each backer to let them know how much of the goals remains for each live campaign that they've pledged. To help them do so we have created the "email_backers_remaining_goal_amount" table saved ```email_backers_remaining_goal_amount.csv``` https://github.com/akhue02/crowdfunding-ETL/blob/main/Crowdfunding-ETL/email_backers_remaining_goal_amount.csv


 To check the queries, see: ```crowdfunding_SQL_Analysis.sql``` (https://github.com/akhue02/crowdfunding-ETL/blob/main/Crowdfunding-ETL/crowdfunding_SQL_Analysis.sql)


## Summary 

As we have seen in this project, the ETL process facilitates performance and helps in performing data analysis on database in an easier and faster way using SQL queries. 
