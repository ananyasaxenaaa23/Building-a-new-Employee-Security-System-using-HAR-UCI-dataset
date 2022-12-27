# Building-a-new-Employee-Security-System-using-HAR-UCI-dataset
Building a new contactless employee check-in system.
-  [**OVERVIEW**](https://github.com/ananyasaxenaaa23/Building-a-new-Employee-Security-System-using-HAR-UCI-dataset/blob/main/README.md#overview)
-  [**SOURCES/USEFUL LINKS**](https://github.com/ananyasaxenaaa23/Building-a-new-Employee-Security-System-using-HAR-UCI-dataset/blob/main/README.md#Useful-links-and-Sources)
-  [**DATA OVERVIEW**](https://github.com/ananyasaxenaaa23/Building-a-new-Employee-Security-System-using-HAR-UCI-dataset/blob/main/README.md#data-overview)
-  [**TARIN AND TEST RATIO**](https://github.com/ananyasaxenaaa23/Building-a-new-Employee-Security-System-using-HAR-UCI-dataset/blob/main/README.md#train-and-test-ratio)
-  [**FRAMEWORK**](https://github.com/ananyasaxenaaa23/Building-a-new-Employee-Security-System-using-HAR-UCI-dataset/blob/main/README.md#framework)
-  [**WORKING OF THE MODEL**](https://github.com/ananyasaxenaaa23/Building-a-new-Employee-Security-System-using-HAR-UCI-dataset/blob/main/README.md#working-of-the-model)

## Overview

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The smartphone will detect the employee's activity using the sensors and then the system connects to the server and determines that person as one of the employees using Gait Analysis. After that the system matches the historical pattern of the employee gait with the current pattern of the employee gate. If the patterns match then the instruction of opening the door automatically will be sent to the application which will be connected with the door sensors.

# Useful links and Sources
For HAR Dataset - https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

## Data Overview

![image](https://user-images.githubusercontent.com/70996037/209675774-f3a8a36c-dcc5-4495-ad9e-bfcbab741423.png)

- Python libraries will be imported.
- After that data loading and pre processing will take place. 
- After that data will be split into two parts training data and testing data.
- After the data will be passed through the model and then the model will give the result.

Accelerometer and gyroscope readings are collected from 30 employees as they complete the 6 activities. Readings are divided into a 2.56 second window with 50% overlap. The accelerometer readings are broken down into readings of gravitational acceleration and body acceleration, which have three X, Y, and Z components. Gyroscope readings are measures of angular velocity that also have X, Y, and Z components.

The jerk signals are calculated from the measured values of body acceleration. After that, all the basic signal values are calculated for each window: mean, maximum, entropy, etc. Then we get a feature vector of 561 features and these features are provided in the dataset.


## Train and Test ratio
30 subjects(**employees**) data is randomly split to __70%__ of the employees were taken as __training data__ and remaining __30%__ subjects’ recordings were taken for __test data__. 

## Framework
### 1. Exploratory Data Analysis(EDA)

- Load the fearure.txt file and then train data and test data.
- Find out the total data points and feature count of the train and test data.
- Investigating the employees activity 
- After plotting a graph it is found that the data is balanced as there are almost same number of reading for each subject.
- A Box Plot is made to plot the Dynamic and Static Activities of the employees.
- At last t-sne has been applied to know how much activities are separable. And after applying t-sne it was seen that all the activities were clean except "Standing" and "Sitting".

### 2. ML Models
Following are the Machine Learning models used.
-	Logistic Regression - In this model, the probabilities describing the possible outcomes of a single trial are modeled using a logistic function.
-	Liner SVC - Linear Support Vector Classifier applies a liner kernel function to perform classification and it performs good with large number of samples.
-	Kernel SVM - It is used as it has a set of mathematical functions used in SVM providing the window to manipulate the data.
-	Decision Tree - It is also called classificationa and regression trees. This method has been used for several tasks for pattern recognition and machine learning as predictive model.
-	Random Forest Classifier - It is used for both classification and regression.It is used to combine multiple classifiers to solve complex problem to improve the performance of the model. It contains a number of decision trees on various subsets of the given dataset and takes the average to improve the predictive accuracy of that dataset.


     ![image](https://user-images.githubusercontent.com/70996037/209705250-9ced8e62-d46f-4a9a-9de9-a2ed20f882c7.png)

     ![image](https://user-images.githubusercontent.com/70996037/209705238-87815da4-3782-43b8-9a5f-5881d95aff18.png)



### 3. Deep Learning Model
-  LSTM model is a type of RNN (Recurrent Neural Network)  which is capable to learn order dependence in sequence prediction models. This remembers the values over arbitary intervals. In this problem it is used to recognize various activities performed by the employees like walking upstairs, walking downstairs and many more.
  ![image](https://user-images.githubusercontent.com/70996037/209706418-a957113b-a58c-4a80-b09c-e109b29e387f.png)
  
  ![image](https://user-images.githubusercontent.com/70996037/209706544-6eaf81ad-ca85-403e-aa21-54af070233e1.png)


## Working of the Model

![image](https://user-images.githubusercontent.com/70996037/209673456-a8974300-8928-4ff5-b5ca-d19bc203731d.png)


- The employee will do an activity which can be Walking, Walking Upstairs, Walking Downstairs, Sitting, Standing and Laying.
- The sensor in the smartphone will collect the Data generated by the employee.
- The data that will be collected by the sensors will be pre-processed by removing the noise from the data.
- Feature extraction will take place which will detect that which activity has been performed by the employee.
- That detail of employee will be sent to the ML model.
- Pattern matching will take place.
