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

#### Around what time of the day do accidents occur the most.

  <img width="590" alt="DV-1" src="https://user-images.githubusercontent.com/60418159/145451007-3bac3f91-4bde-4f39-821c-997c117e28b5.PNG">

  Most time of the day accidents occur is 'Working office hours (10-16)'. Looks like there are approximately above 350,000 count of accidents that have taken place in the Working Office Hours from 10am to 4pm. The second highest for count of accidents is around evening time from 6pm to 10pm. The least count of accidents occurred around nighttime from 10pm to 6am with a count of approximately 100,000. Looks like during 10am to 4pm there are more chances of people travelling a lot, as it is office hours or school hours or business hours etc. So, we can clearly see even the count of accidents are morning during working hours.

#### Average Number of Casualties based on part of a Day

  <img width="746" alt="DV-2" src="https://user-images.githubusercontent.com/60418159/145451684-f466f15c-b11a-4f73-b202-b12b20e0c4c2.PNG">

  Night time from 10pm to 6am has more number of casualties compared to the others. The second highest is Working hours from 10am to 4pm. The least average number of casualties is in the Rush in the Morning from 6am to 10pm. So there were more number of casualities during the Night time. The reason might be due to bad lighting which might have been the reason for accidents to occur with more casualties.

#### Average Number of Casualties based on Speed Limit in part of a day

 ![DV-3](https://user-images.githubusercontent.com/60418159/145451780-3486134e-63da-4dc0-9808-8b1f78fec8c5.png)
 
 More number of casualties were with highest speed of 70mph. The second highest average of casualties is 70mph. The least number of accidents were from 20mph. So, more speeding can result in more casualties.
 
 #### Total count of Accidents on Weekly basis
 
  ![DV-4](https://user-images.githubusercontent.com/60418159/145451898-230d236c-8563-4c6c-8309-78db779a8e3b.png)

 Highest number of accidents occurred were on Friday and the next highest is Thursday. The least number of accidents occurred were on Sunday. Since most number of accidents occurred on Friday it means there are more number of people travelling on Friday due to weekend.
 
 #### Total Number of Accidents on Yearly basis

  ![DV-5](https://user-images.githubusercontent.com/60418159/145452021-6a6e3f9a-250f-43e7-8385-2116b2cfac22.png)

 There are more accidents in 2016, then the second highest was in 2018. The least number of accidents occurred in 2019. There were approximately above 300,000 number of accidents in 2016, but there was a drastic change in 2019 because the count was approximately below 150,000 which is less than half of what occurred in 2016. So the count of total accidents has reduced gradually compared to 2016, this means that there are necessary steps taken to prevent accidents from occurring, but there is a slight increase in 2020 as compared to 2019. The count can become less if there are more precautions taken.
 
 #### Total count of Severity of Accidents on yearly basis
 
   <img width="714" alt="DV6-1" src="https://user-images.githubusercontent.com/60418159/145452589-76d0ceac-5102-4d45-b609-e9247a7ee1d3.png">
 
 I can see that there is a huge variation in Slight severity of accidents which was highest in 2016 and was low in 2019 whereas the Fatal and Serious count was approximately similar in all the years.
 
 #### Total accidents that occur Monthly based on Severity
 
   <img width="739" alt="DV7-1" src="https://user-images.githubusercontent.com/60418159/145452614-35885137-df1e-4860-a609-abeb604f1921.png">

Looks like Slight severity has been the highest count and the least is Fatal severity. But when we compare on monthly basis when we move the cursor onto the lines, we can see that the number of accidents with 'Slight' severity have been increasing in the month of October and November, this could be due to holiday season and people are mostly prone to coming out. They have been low around the starting of the year.'Serious' and 'Fatal' are being consistent in every month throughout all the years.

#### Road and weather Conditions subplots

   ![DV-8](https://user-images.githubusercontent.com/60418159/145452517-1a2409cb-8fbd-4eb3-ad30-159ebd831786.png)

   Surprisingly accidents were not mostly based on climatic changes or road changes or surface conditions or road type. It looks like more accidents did take place while most of the conditions were normal.
 
 ####  Accidents based on Age Band of Driver and Gender

 <img width="399" alt="DV-9" src="https://user-images.githubusercontent.com/60418159/145453186-258aa338-ebd6-454c-859a-db6e77f02b5d.PNG">
    
  Male population is more prone to accidents compared to Female population. There are about 33% of Female gender and 68% of Male gender who are prone to accidents.
    
 ![DV-10](https://user-images.githubusercontent.com/60418159/145453228-3cd0e85e-8685-4119-b941-135f281ba472.png)

  We can see that the age band between 26-35 have highest count of accidents for both male and female genders. The second highest count is 36-45. So from this graph, I     can analyse that as the age reduces the accidents are being less.
 
 #### Maps

  <img width="939" alt="Map 1" src="https://user-images.githubusercontent.com/60418159/145453327-e3748f49-367a-4000-9553-6ff027c6f30c.png">
 
   I used Folium and using Latitude and Longitude columns I potted the map to show where accidents have occurred. This can help us find the area where accidents frequently  occur, and necessary steps can be taken to prevent them. 
 
 ![map 2](https://user-images.githubusercontent.com/60418159/145453356-2f9bf582-ca2e-4580-ad58-41bcd74330c0.png)
 
 Map is presenting rural and urban areas. There were more accidents in urban area compared to rural.
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 







