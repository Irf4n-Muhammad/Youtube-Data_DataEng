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

[](#)
[](#)
[](#)

## 1. Description of the Problem:
Today, analysts use historical data from platforms like YouTube to build predictive models for better user engagement and smarter decision-making. But these models face challenges due to the changing nature of online video consumption, which can be influenced by trends, world events, and audience preferences.

Moreover, when dealing with global data, complexities arise due to cultural and regional variations in content consumption. Hence, it's important to combine data analysis with current context and trends to drive better business decisions.

## 2. Objective:
Historical YouTube data is a rich resource for content creators, marketers, and analysts, helping them understand audience habits, predict content demand, and formulate content strategies.

These datasets can also optimize content recommendations and planning, and guide strategic decisions for platforms like YouTube. Plus, they provide academic and research opportunities, allowing exploration of viewer behavior and the influence of video platforms on global media consumption.

<img src="https://github.com/Irf4n-Muhammad/Youtube-Data_DataEng/assets/121205860/7e8e7f58-51a3-4d72-bdc8-d2490365d6a9" width="500" height="300">

A typical YouTube dataset, available as .csv files or via APIs, includes various engagement metrics but has limitations. It captures historical trends but may not predict sudden changes or account for local contexts. Therefore, it's essential to consider these limitations when using this data. Moreover, we must handle this data responsibly, ensuring user anonymity and data privacy. This project aims to analyze YouTube data using AWS and visualize the results, helping uncover patterns and insights into user behavior and content performance on YouTube.

## 3. Technologies:
In this project, we gonna leverage some AWS services:

 - AWS S3
 - AWS IAM
 - AWS Glue
 - AWS Catalog
 - AWS lambda
 - AWS athena
 - AWS Redshift

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





