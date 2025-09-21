##                    End-End Power BI Dashboard Development
![Project-Patient-Wait-List](https://github.com/user-attachments/assets/f1678a63-11dd-44dd-92e3-f3714d0fe41f)
##  The process of creating a dashboard in Power BI consist of following steps:  
1. Requirement Gathering
2. Data Collection
3. Data Transformation & Modelling
4. Data Visualization Blueprint
5. Dashboard Layout & Design
6. Adding Interactivity & Navigation
7. Testing
8. Sharing
9. Maintenance & Routine Refresh
- Now lets see all of these steps in detail and develop a Power BI dashboard from scratch. For this exercise we will be using publicly available Healthcare data about the Patient Waiting List.
  
## You can download the resources used in this entire process from the above github csv files
note: combine all the files make a folder as all_data
1. Identify Stakeholders

- Determine primary stakeholder and establish a point of contact who might be the domain experts or leaders who will eventually use the dashboard

2. Understand Business Objectives 

- Through meetings and calls  with stakeholders you should get an outline of Goals from the entire endeavor. Asking open ended questions will help you gain more insights to understand the data and how this dashboard will help achieve a specific business goa
3. High Level Data Study

- A high level overview of data is required before you initiate discussions around scope, metrics and other granular topics. So here we will try to understand the data in terms of:

1. Data Sources
2. Column Description
3. Data Type
4. Volume and frequency
5. Data Quality – Missing Values or Anomalies

4.Define Scope

- This is the perfect stage to discuss Key Metrics, KPIs & Deployment Timelines. Document the calculations, time frames & scope which will help in setting the expectations and avoiding any future disagreements. Also as a best practice remember to keep a 20% buffer while finalizing deadlines because it’s always better to over deliver after a standard commitment than to underdeliver after an extraordinary delivery pitch.

## What is the problem statement for this exercise?
 Overall Objective
1. Track current status of patient waiting list
2. Analyze historical monthly trend of waiting list in Inpatient & Outpatient categories
3. Detailed specialty level & age profile analysis

Data Scope
2018 – 2021

Metrics
1.  Average & Median Waiting List
2. Current Total Wait List

View
1. Summary Page
2. Detailed Page for Granular Analysis

## 2.Data Collection
There are over 200 different data connectors available to collect data inside power bi, but below are the most widely used connectors:

1. Excel / CSV
2. Folder Connection
3. SQL Server or Any database
4. Power BI services
5. Cloud Platforms – Azure, AWS, GCP etc.
6. ERP Systems – Salesforce, SAP etc.
7. Sharepoint
8. Web or JSON

   
steps by step to how connect to data source:
1. Open Power BI desktop and click on GET DATA and select FOLDER option. Click Connect button at the bottom right
![unnamed](https://github.com/user-attachments/assets/d7b3d6e2-bc7c-43b7-9ea4-ef4707329a88)

2. Now browse the folder path where we have stored all_data and press ok
<img width="528" height="169" alt="unnamed" src="https://github.com/user-attachments/assets/8249a732-42fc-413d-8fe2-929fb751182b" />

3. The next prompt will show you the files available in the folder path. Then click on Combine button and select Combine & Load


##  3.Data Transformation
Data transformation is a process of changing the structure of your data or applying additional steps which will clean or process your data for final usage. We do these transformations in the Power Query Editor which is inbuilt into Power BI.
<img width="1600" height="516" alt="unnamed" src="https://github.com/user-attachments/assets/42eb0d2b-dc56-491c-bc45-b10cd96f6349" />

Now for this project purposes we will mainly see below steps:

1. Renaming Columns
2. Rearranging Columns
3. Appending 2 Tables
4. Replacing & trimming values

Data Modelling

- Data modelling is a way to create relationship with one table to another, so that we can fetch valuable information from them in our reporting layer.
- Lets jump into the Data Modelling View, which is located at the left hand panel on Power BI.

We will be using All_Data from now onwards, so we can safely hide inpatient and outpatient data. We can also stop it from loading into the data model by disabling it from the power query editor. Just right click on the table name in power query and uncheck Enable Load.

Now since specialty name is one of the key attributes that we are looking in this project, lets focus on that column now. As you have seen in the data, we have a huge number of specialty available and using all of them in our report layer directly will create a clutter in our visualization. A better approach would be to distribute them in buckets. So to do this I have created a specialty mapping file which you will find in the downloaded resources. Lets import that file in power bi to create the relationship with All_Data.

Once you import this file, Power BI should auto detect relationship and connect both the tables. However if it does not then you can do it manually by following below steps:

1. Go to the model view
2. Click on Specialty_Name column in All_Data
3. Drag this column over the Specialty column in Mapping table
Now you should see a line connecting both the tables and an arrow pointing towards All_Data from Mapping table. This means that we have created a relationship between both the tables. The arrow signifies the filter context and tells you that now you can use columns from Mapping table to filter data in All_Data.
