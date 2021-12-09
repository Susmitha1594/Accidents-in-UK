# Accidents-in-UK
### Overview
Road accidents have been a major concern for all the countries around the world. According to WHO approximately 1.3 million people die every year because of road traffic. These result in death and injuries of many people. Using data science could be helpful in identifying the major reasons of occurrence of accidents and help in resolving the problems. By using the Open Road Safety Data for past 5 years of UK (2016-2020) datasets, which are available in the government website, I will perform data analysis. The main aim of the project is to analyze the data, plot various Data Visualization graphs and implement different Machine Learning algorithms and finally evaluate the model that gives better accuracy in predicting the accidents severity which will help the police department to identify the reason for accidents and take necessary actions to provide safety of the people.

### Data Source
Data was collected from government website of UK (https://data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data). This data is published from Department of Transport frequently. For this project, I have used three CSV files that was published on 14th October 2021:
1.	Road Safety - Accidents last 5 years
2.	Road Safety - Vehicles last 5 years
3.	Road Safety - Casualties last 5 years

There is another excel file which is available that gives us information on all the Code values with their labels. That excel file is 'Road Safety Open Dataset Data Guide.xlsx' which is found under supporting documents on the website given above.

### Steps performed for analysis
1. Data Collection
2. Data Pre-processing
3. Data Visualization
4. Data Modeling
5. Evaluation of the results

### Data Collection

I have used the three datasets which are available in the government website. Accident, Vehicles, Casualties datasets. Initially using Merge command, I combined all the csv files into a single data frame using a common column ‘accident_index’ which is present in all the three datasets. I used this data frame for my entire analysis. After combining all the csv files, I have a total of 1229470 rows and 79 columns.

### Data Pre-processing

Since we have many rows and columns cleaning the data is the first step we do. Initial   step was to clean null values. So, I calculated the number of null values in each row the I removed few columns which had more null values and will not be useful for our analysis. The values in 
the dataset mostly consisted of code values and the labels for each code was present in 'Road      Safety Open Dataset Data Guide.xlsx’, so using this code values I converted few columns to categorical values which would be helpful for Data Visualization.

### Data Visualization

* 1)	Around what time of the day do accidents occur the most

