# Data Engineering Project / Youtube Data Analysis

## 1. Description of the Problem:
Today, analysts use historical data from platforms like YouTube to build predictive models for better user engagement and smarter decision-making. But these models face challenges due to the changing nature of online video consumption, which can be influenced by trends, world events, and audience preferences.

Moreover, when dealing with global data, complexities arise due to cultural and regional variations in content consumption. Hence, it's important to combine data analysis with current context and trends to drive better business decisions.

## 2. Objective:
Historical YouTube data is a rich resource for content creators, marketers, and analysts, helping them understand audience habits, predict content demand, and formulate content strategies.

These datasets can also optimize content recommendations and planning, and guide strategic decisions for platforms like YouTube. Plus, they provide academic and research opportunities, allowing exploration of viewer behavior and the influence of video platforms on global media consumption.

<img src="https://github.com/Irf4n-Muhammad/Youtube-Data_DataEng/assets/121205860/7e8e7f58-51a3-4d72-bdc8-d2490365d6a9" width="500" height="300">

A typical YouTube dataset, available as .csv files or via APIs, includes various engagement metrics but has limitations. It captures historical trends but may not predict sudden changes or account for local contexts. Therefore, it's essential to consider these limitations when using this data. Moreover, we must handle this data responsibly, ensuring user anonymity and data privacy. This project aims to analyze YouTube data using AWS and visualize the results, helping uncover patterns and insights into user behavior and content performance on YouTube.

## 3. Technologies:

The choosen technologies is variative and depends on the case and condition. There are some option for certain case and in this case, I am using this option since it's the easiest.

- Dockerfile
- Docker Compose
- VM GCP
- Airflow / Prefect
- GCS (Google Cloud Storage)
- Bigquery
- DBT cloud / Spark
  DBT is best for this case for several reason:
  1. The file's size is small (2 GB)
  2. DBT provide the docuementation
- Google Data Studio

## 4. Data Architecture:
<img width="700" alt="image" src="https://github.com/Irf4n-Muhammad/Data-Engineering-Project_COVID19-Dataset/assets/121205860/17f49dd3-604f-496e-9ea6-63ea6004deac">



## 5. Data Description:

The datasets that we'll be using for this analysis are comprehensive and varied, offering different granularities of data. These are as follows:

- full_grouped.csv: This dataset provides daily updates on the number of COVID-19 cases. The unique aspect of this data file is that it goes beyond the country level, incorporating the number of cases at the county, state, and province level. This comprehensive breakdown allows us to analyze not only the overall impact on a given country but also how the virus is affecting specific regions within those countries.

- covid_19_clean_complete.csv: Like the previous dataset, this also provides day-to-day updates on the number of COVID-19 cases per country. However, unlike full_grouped.csv, it does not offer data at the county, state, or province level. This dataset can be used for a broad overview of the impact on each country as a whole.

- country_wise_latest.csv: This dataset offers the most recent snapshot of the number of COVID-19 cases on a country level. It is useful for getting an up-to-date overview of the current situation in each country.

- day_wise.csv: This dataset offers a daily summary of the number of COVID-19 cases. However, it does not provide country-level data. This global overview can provide insights into the overall trends and pace of the pandemic.

- usa_county_wise.csv: This dataset provides a granular look at the day-to-day number of COVID-19 cases at the county level within the United States. This allows for a detailed understanding of how the pandemic is affecting different regions within the US.

- worldometer_data.csv: The final dataset is sourced from Worldometer, a reputable reference website that provides real-time statistics for a wide variety of topics. This dataset provides the most recent data on the number of COVID-19 cases and can offer valuable insights into the current state of the pandemic.

These data was collected from kaggle : https://www.kaggle.com/datasets/imdevskp/corona-virus-report

