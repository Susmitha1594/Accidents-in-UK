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

Since we have many rows and columns cleaning the data is the first step we do. Initial   step was to clean null values. So, I calculated the number of null values in each row the I removed few columns which had more null values and will not be useful for our analysis. The values in the dataset mostly consisted of code values and the labels for each code was present in 'Road Safety Open Dataset Data Guide.xlsx’, so using this code values I converted few columns to categorical values which would be helpful for Data Visualization.

### Data Visualization

#### Around what time of the day do accidents occur the most.

  <img width="590" alt="DV-1" src="https://user-images.githubusercontent.com/60418159/145451007-3bac3f91-4bde-4f39-821c-997c117e28b5.PNG">

  Most time of the day accidents occur is 'Working office hours (10-16)'. Looks like there are approximately above 350,000 count of accidents that have taken place in the Working Office Hours from 10am to 4pm. The second highest for count of accidents is around evening time from 6pm to 10pm. The least count of accidents occurred around nighttime from 10pm to 6am with a count of approximately 100,000. Looks like during 10am to 4pm there are more chances of people travelling a lot, as it is office hours or school hours or business hours etc. So, we can clearly see even the count of accidents are morning during working hours.

#### Average Number of Casualties based on part of a Day

  <img width="746" alt="DV-2" src="https://user-images.githubusercontent.com/60418159/145451684-f466f15c-b11a-4f73-b202-b12b20e0c4c2.PNG">

  Night time from 10pm to 6am has more number of casualties compared to the others. The second highest is Working hours from 10am to 4pm. The least average number of casualties is in the Rush in the Morning from 6am to 10pm. So there were more number of casualties during the Night time. The reason might be due to bad lighting which might have been the reason for accidents to occur with more casualties.

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

Looks like Slight severity has been the highest count and the least is Fatal severity. But when we compare on monthly basis when we move the cursor onto the lines, we can see that the number of accidents with 'Slight' severity have been increasing in the month of October and November, this could be due to holiday season and people are mostly prone to coming out. They have been low around the starting of the year. 'Serious' and 'Fatal' are being consistent in every month throughout all the years.

#### Road and weather Conditions subplots

   ![DV-8](https://user-images.githubusercontent.com/60418159/145452517-1a2409cb-8fbd-4eb3-ad30-159ebd831786.png)

   Surprisingly accidents were not mostly based on climatic changes or road changes or surface conditions or road type. It looks like more accidents did take place while most of the conditions were normal.
 
 ####  Accidents based on Age Band of Driver and Gender

 <img width="399" alt="DV-9" src="https://user-images.githubusercontent.com/60418159/145453186-258aa338-ebd6-454c-859a-db6e77f02b5d.PNG">
    
  Male population is more prone to accidents compared to Female population. There are about 33% of Female gender and 68% of Male gender who are prone to accidents.
    
 ![DV-10](https://user-images.githubusercontent.com/60418159/145453228-3cd0e85e-8685-4119-b941-135f281ba472.png)

  Age band between 26-35 have highest count of accidents for both male and female genders. The second highest count is 36-45. So from this graph, we can analyze that as the age reduces the accidents are being less.
 
 #### Maps

  <img width="939" alt="Map 1" src="https://user-images.githubusercontent.com/60418159/145453327-e3748f49-367a-4000-9553-6ff027c6f30c.png">
 
   Using Folium and columns form the table Latitude and Longitude, I potted the map to show where accidents have occurred. This map gets stored as html file. I just placed a sample screenshot, but for full map I have placed in the documents list. This can help us find the area where accidents frequently  occur, and necessary steps can be taken to prevent them. We can see few spotting that
 
 ![map 2](https://user-images.githubusercontent.com/60418159/145453356-2f9bf582-ca2e-4580-ad58-41bcd74330c0.png)
 
 Map is representing rural and urban areas. There were more accidents in urban area compared to rural areas.
 
 
 ### Data Modeling
 
We will work on using few **Supervised Learning algorithms** to check the Accident Severity and to predict which model will give a better accuracy. It is very important to make sure the model predicts well because there are high chances of getting into trouble if there are more False Negative, which means predicting an area which is prone to more accidents as negative. This can be dangerous. So here we have checked for Predicting the Severity of Accidents. After splitting the data in Train and Test sets, we have performed few algorithms to check the prediction.

#### Gaussian Naive Bayes

It is an easy and simple classifier to apply. It can handle working with both discrete and continuous data. It can be used to make real time predictions and the execution speed is quick.

<img width="452" alt="GNB" src="https://user-images.githubusercontent.com/60418159/145462986-e255b4f2-19ca-4416-b42e-a1813bac6329.png">

The results shows that we got an accuracy of 63% which is not very great. Recall was about 63%, Precision was 87% and F1-Score being 63%. Coming on to confusion matrix it has predicted Slight more correctly than the rest but the prediction was less for the others. Overall the Accuracy is 63%. The time taken for execution is 236ms.

#### KNN

K Nearest Neighbors (KNN) involves on getting data from the original data point to the closest datapoint based on the K datapoints. KNN has a good advantage even if we add new data in the middle as it chooses the closest data and doesn’t have to make another new model, the prediction gets adjusted accordingly. Using KNN model by selecting the n_neighbors as 4 to find the accuracy.
  
<img width="414" alt="KNN" src="https://user-images.githubusercontent.com/60418159/145463119-b3c32b16-cc0b-4ac1-98cd-6e23d9157e61.png">

The results of KNN shows that the Accuracy is 76% which seems better than Naive Bayes. Recall, Precision and F1 scores all look approximately equal to 76%. True positives have also improved in prediction than above model. But the disadvantage lies when the execution time was taking longer. It took about 46mins for it to run. 


#### Logistic Regression

Logistic Regression will perform well when the data is fit for it. It is very quick in classifying unknown records. 

<img width="420" alt="LR" src="https://user-images.githubusercontent.com/60418159/145463204-89d737d1-1b82-41da-a695-e55b0750714d.png">

The results from Logistic Regression are where Accuracy was 78%. Precision score was little less 67%. Recall and F1 Score was 78%. Accuracy score looks better compared to above two models.

#### Decision Tree

Decision Tree is one of the popular machine learning algorithms. It solves the problem by converting the data into tree format. Each node represents an attribute, and each leaf node represents a class label.

<img width="386" alt="DT" src="https://user-images.githubusercontent.com/60418159/145463263-1f6233a1-5712-4c30-a418-016a57fc85aa.png">

The results from the Decision tree look great compared to all the above models with an Accuracy of 95% in predicting the Severity of accidents. Recall, Precision and F1-scores look good with 95% each. The time taken for the execution of the model is less with 108ms. 

#### Random Forest

Random Forest classifier constructs a forest with an ensemble of decision trees. It works well with more categorical and numerical data. It implicitly performs feature selection and gives uncorrelated Decision trees. 

<img width="442" alt="RF" src="https://user-images.githubusercontent.com/60418159/145463280-046107d1-912c-4342-aa24-f48804db15be.png">

The results are that Accuracy is the highest of all the models including Decision Tree which is 96%. Recall, Precision and F1 scores are also high compared to all which shows that Random Forest Model has given the best Accuracy Prediction to check Severity of Accidents. The time taken for execution is also very less 10s compared to all the models.


### Final Analysis

Accidents in UK has given a lot of information from the analysis. From my analysis I can say that, accidents mostly occurred during the Working hours which is from 10am to 4pm and number of casualties were also more during this time. Accidents mostly even occurred when people were travelling in high speed, from the results people who drove with 70mph were prone to accidents. There were more accidents during Friday compared to other days, the reason could be due to weekend and looks like more people are coming out on Friday. On yearly basis I could see that accidents have reduced quite well. Especially in the year 2019, 2020 the total number of accidents were comparatively less. One reason I feel is, it might be due to COVID where number of people travelling would reduce. On Monthly basis, I could see more accidents around November and December in Plotly graphs. As these months are during holiday seasons it could be that more people come out than usual. So maybe more traffic could cause accidents. Coming on to Severity of accidents, I could see that there were more Slight accidents compared to Serious and Fatal ones which were low. This might be due to following wrong traffic signals or not stopping at stop signs etc. While plotting subplots I was surprised to see most of the accidents occurred when Weather conditions were normal with no high winds, as I expected more accidents when weather conditions are bad, but this didn’t happen in this case. Accidents were also less when Road Surface conditions were Dry and when there were no Special conditions as well. So, from this we can say that accidents were not caused due to any change in Weather, Road Surface conditions, Road Type or Special Conditions on site. They occurred when everything was normal. From the gender point of view, I could see that more Males were involved in accidents compared to Females. From the age band I could see mainly younger generation from 26-35. Looks like younger generation drive carelessly compared to other age groups.

Machine Learning Algorithms for Predicting Severity of Accidents: 

Finally coming on to Predicting the Severity of Accidents. I did perform five Supervised algorithms which were Gaussian Naïve Bayes, KNN, Logistic Regression, Decision Tree and Random Forest Classifier. The accuracy for Gaussian Naïve Bayes was 63% and time for execution took about 236ms. Accuracy for KNN was 76% and the execution time was 46mins which was quite longer and might not be the best while checking accuracy every time as time consumption is more. In Logistic regression the accuracy was 78% and time for execution was 79ms. Decision Tree classifier gave an accuracy of 95% which is the best score out of all the algorithms and the time taken for execution is 108ms. Lastly, I worked on Random Tree Classifier which gave an accuracy of 96% and execution time was about 10s.
From all the above analysis, the best prediction was given by Random Forest Classifier which gave the highest accuracy of 96% and the time taken was also 10s which was the least timing among all the execution time. So for the dataset Random Forest has given the highest accuracy in predicting the severity of accidents.

This analysis can be helpful for either police department or government of UK in taking necessary steps and to reduce the number of accidents from occuring.


#### References

1) https://medium.com/@himanshuit3036/supervised-learning-methods-using-python-bb85b8c4e0b7

2) https://machinelearningmastery.com/naive-bayes-tutorial-for-machine-learning/

3) https://towardsdatascience.com/understanding-confusion-matrix-a9ad42dcfd62

4) https://stats.stackexchange.com/questions/285834/difference-between-random-forests-and-decision-tree

5) https://www.simplilearn.com/tutorials/machine-learning-tutorial/naive-bayes-classifier

6) https://dhirajkumarblog.medium.com/top-5-advantages-and-disadvantages-of-decision-tree-algorithm-428ebd199d9a

7) https://medium.datadriveninvestor.com/random-forest-pros-and-cons-c1c42fb64f04



 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 







