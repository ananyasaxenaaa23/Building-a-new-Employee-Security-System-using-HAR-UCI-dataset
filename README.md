# Building-a-new-Employee-Security-System-using-HAR-UCI-dataset
Building a new contactless employee check-in system.
-  [**OVERVIEW**](https://github.com/ananyasaxenaaa23/Building-a-new-Employee-Security-System-using-HAR-UCI-dataset/edit/main/README.md#overview)
-  [**SOURCES/USEFUL LINKS**](https://ghttps://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones#Useful-links-and-Sources)
-  [**DATA OVERVIEW**](https://ghttps://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones#data-overview)
-  [**TARIN AND TEST RATIO**](https://ghttps://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones#train-and-test-ratio)
-  [**FRAMEWORK**](https://ghttps://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones#framework)


## Overview

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

## Useful links and Sources
For HAR Dataset - https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

## Data Overview
Accelerometer and gyroscope readings are collected from 30 employees as they complete the 6 activities. Readings are divided into a 2.56 second window with 50% overlap. The accelerometer readings are broken down into readings of gravitational acceleration and body acceleration, which have three X, Y, and Z components. Gyroscope readings are measures of angular velocity that also have X, Y, and Z components.

The jerk signals are calculated from the measured values of body acceleration. After that, all the basic signal values are calculated for each window: mean, maximum, entropy, etc. Then we get a feature vector of 561 features and these features are provided in the dataset.


## Train and Test ratio
30 subjects(*employees*) data is randomly split to __70%__ of the employees were taken as __training data__ and remaining __30%__ subjects’ recordings were taken for __test data__. 

## Framework
## 1. Exploratory Data Analysis(EDA)

- Load the fearure.txt file and then train data and test data.
- Find out the total data points and feature count of the train and test data.
```python
features = list()
with open('/content/drive/MyDrive/UCI HAR Dataset-20221223T170042Z-001/UCI HAR Dataset/UCI HAR Dataset/features.txt') as f:
    features = [line.split()[1] for line in f.readlines()]
print('Total Features: {}'.format(len(features)))

```

```
Output: 
(7352, 564) (2947, 564)

```

- Investigating the employees activity 
```
sns.set_style('darkgrid')
plt.rcParams['font.family'] = 'sans-serif'

plt.figure(figsize=(20,10))
plt.title('Data of Employees', fontsize=20)
sns.countplot(x='subject',hue='Act_emp_Name', data = train)

plt.show()

```
 ![npic1]()
