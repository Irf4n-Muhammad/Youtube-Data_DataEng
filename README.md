# Data Engineering Project / Youtube Data Analysis

## List of Contents:
1. [Description of the Problem](#1-description-of-the-problem)
2. [Objective](#2-objective)
3. [Technologies](#3-technologies)
4. [Data Architecture](#4-data-architecture)
5. [Data Description](#5-data-description)  
   1. [CSV Files](#51-csv-files)  
   2. [JSON Files](#52-json-files)
6. [AWS Set up](#6-aws-set-up)  
   1. [Sign up the account](#61-sign-up-the-account)  
   2. [Connect the AWS CLI](#62-connect-the-aws-cli)
7. [AWS S3 (Raw File Bucket)](#7-aws-s3-raw-file-bucket)
8. [AWS Glue](#8-aws-glue)
9. [AWS Athena](#9-aws-athena)
10. [AWS Lambda](#10-aws-lambda)

## 1. Description of the Problem:
Today, analysts use historical data from platforms like YouTube to build predictive models for better user engagement and smarter decision-making. But these models face challenges due to the changing nature of online video consumption, which can be influenced by trends, world events, and audience preferences.

Moreover, when dealing with global data, complexities arise due to cultural and regional variations in content consumption. Hence, it's important to combine data analysis with current context and trends to drive better business decisions.

## 2. Objective:
Historical YouTube data is a rich resource for content creators, marketers, and analysts, helping them understand audience habits, predict content demand, and formulate content strategies.

These datasets can also optimize content recommendations and planning, and guide strategic decisions for platforms like YouTube. Plus, they provide academic and research opportunities, allowing exploration of viewer behavior and the influence of video platforms on global media consumption.

<img src="https://github.com/Irf4n-Muhammad/Youtube-Data_DataEng/assets/121205860/415f0d75-7ecd-4bdd-a3f7-21dcc9d75ea2" width="500" height="300">

A typical YouTube dataset, available as .csv files or via APIs, includes various engagement metrics but has limitations. It captures historical trends but may not predict sudden changes or account for local contexts. Therefore, it's essential to consider these limitations when using this data. Moreover, we must handle this data responsibly, ensuring user anonymity and data privacy. This project aims to analyze YouTube data using AWS and visualize the results, helping uncover patterns and insights into user behavior and content performance on YouTube.

## 3. Technologies:
In this project, we gonna leverage some AWS services:

 - AWS S3
 - AWS IAM
 - AWS Glue
 - AWS lambda
 - AWS athena

## 4. Data Architecture:
<img src="https://github.com/Irf4n-Muhammad/Youtube-Data_DataEng/assets/121205860/a08ba9c3-f337-4147-b995-24544332a5b5" width="700" height="400">


## 5. Data Description:

### 5.1 CSV Files:

These files contain historical video data from YouTube for different countries. They include video IDs, viewing durations, user interests, popular content, and more. The data helps understand viewer behavior and video performance trends in respective regions.

- CAvideos.csv: Data for Canada
- DEvideos.csv: Data for Germany
- FRvideos.csv: Data for France
- GBvideos.csv: Data for the United Kingdom
- INvideos.csv: Data for India
- JPvideos.csv: Data for Japan
- KRvideos.csv: Data for South Korea
- MXvideos.csv: Data for Mexico
- RUvideos.csv: Data for Russia
- USvideos.csv: Data for the United States

### 5.2 JSON Files:

These files map the category IDs to their corresponding categories for videos from different countries, assisting in understanding popular content categories in respective regions.

- DE_category_id.json: Category data for Germany
- FR_category_id.json: Category data for France
- GB_category_id.json: Category data for the United Kingdom
- IN_category_id.json: Category data for India
- JP_category_id.json: Category data for Japan
- KR_category_id.json: Category data for South Korea
- MX_category_id.json: Category data for Mexico
- RU_category_id.json: Category data for Russia
- US_category_id.json: Category data for the United States

These data was collected from kaggle : https://www.kaggle.com/datasets/datasnaek/youtube-new

## 6. AWS Set up:
In this first section, we gonna create the account and connect the AWS CLI to our local computer

### 6.1 Sign up the account:
1. Sign up to the AWS using root account (use your email)
2. Go to the AWS IAM and create the new user there, this user will be used as our main system since the root account it's a bit risk to be used (since it contains all the important information)
3. After you create the user, download the csv file and logout from the account.
4. Log in again using your user account (the register information is included in your csv file)

### 6.2 Connect the AWS CLI:
1. It would be different for different OS, please check and open AWS CLI for more information.
2. Open your terminal/ Git Bash
3. Running the ( aws configure )
4. Add all your personal information from your account
- AWS Access Key ID
- AWS Secret Access Key
- Default region name: The region code of the default region (e.g., us-east-1).
- Default output format: The output format for the AWS CLI (e.g., json).


## 7. AWS S3 (Raw File Bucket)
This tools will provide the bucket which will be used to store our file
1. Create the main table for our raw file
2. You can use the name of the combination of your project and the region that you use

Along the process we will back to create the new bucket, so keep in mind to always specify the name of your bucket.
For example (your main bucket name)-(your specific task using this bucket)

3. Download the data from the data source. In case from kaggle, then create the new directory and copy API Command from kaggle and paste that in git bash.
4. Zip the zip file
5. Send the folder into S3 Bucket using git bash

## 8. AWS Glue:
This tools can help to read the schema and create the catalog (ETL Process), which eventually can be created a table and we can use the AWS Athena afterwards.
1. Create the crawler glue
2. Then we create the role for the crawler (specify glue name in your glue role)
3. Set the role:
   - AmazonFullAccess
   - AWSGlueServiceRole
     
4. Create the new database for AWS Glue
5. Open the table and we would find some information about json (column name, etc)
6. Click action and click the view data
7. And it will open AWS Athena

## 9. AWS Athena:
We can transform the data without moving it data warehouse like reshifts or in other words, we transform on top of the data and can be stored again it in the S3 bucket.

1. Click setting and manage
2. Create the new bucket, in particular for AWS Athena
3. Try to run, we will find there is error
4. The issue is the json file has unreaded json format. So we have to edit this to be fitted with the AWS or in other words, we clean the data from semi structured data to structured data.
   
<img width="500" alt="image" src="https://github.com/Irf4n-Muhammad/Youtube-Data_DataEng/assets/121205860/61eb2e6e-acc3-4f6e-9510-e6a39d1bbd25">

5. So in this case, we will use AWS lamda to clean and store in the bucket.

 ## 10. AWS Lambda:
 1. Firstly, create the function and give AmazonFullAccess
 2. Open the AWS Lamda and put the python file (which will help us to clean the data)
 3. Click configuration and click the environment variable set several variable that same on our python file
 4. Try to setting the run and choose S3 put. Then input yoru bucket and the link of one of your file
 5. If there is an error, then scroll down and you'll find 'add layer'. Choose DataWrangler or SDKPandas and choose the latest version
 6. If there is an error about timeout, then click the configuration and then click the general button (on the top) and set the timeout to be maybe 3 minutes (You can adjust it as like as you want)
 7. Try to run it again and it should work (make sure your connection is good)

    
    







