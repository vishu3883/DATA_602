
  
 
## CRIME INCIDENT REPORTS
Officers of the Boston Police Department (BPD) prepare crime incident reports to keep track of the early circumstances surrounding an occurrence. consisting of a smaller number of fields aimed for gathering information on an incident's specifics, such as when and where it took place. Objective - I want to be able to anticipate when crimes will take place based on the kind of offense committed and the time of day.

### Dataset Description:
Dataset had been extracted from the crime incident reports of Boston Police Department "Analyze Boston". This dataset contains the the crimes which are done and they are categorized by the type of offense they are involved in the year 2022

### Access to Dataset: 
https://data.boston.gov/dataset/crime-incident-reports-august-2015-to-date-source-new-system/resource/313e56df-6d77-49d2-9c49-ee411f10cf58

Initially, The dataset consists of 18941 observations & 17 Columns.

#### INCIDENT_NUMBER:
 Unique Number for the each offense recorded
 
 #### OFFENSE_CODE: 
 Each Type of Offense has unique code according to the type of Offense

#### OFFENSE_CODE_GROUP:
In which group of categories the offenses are categorized.
#### OFFENSE_DESCRIPTION: 
It involves types of offenses they are committed such as {Burglary, theft, loss of property or an item}

#### DISTRICT: 
In which district these offenses were took place and each offense has a unique code.

#### REPORTING_AREA: 
For the better picture of the offense and to differentiate from the other areas there different set of areas with a unique number to them.

#### SHOOTING: 
If that offense included Shooting or not

#### OCCURRED_ON_DATE: At which date the incident took place and this column gives us the time of the incident.

#### YEAR: In which year all this offense took place Here we are taking year wise data from the Boston Police department for this dataset I have taken year 2021 dataset.

#### MONTH: 
In which month of the year the offenses were took place.
	
#### DAY_OF_WEEK:
On which days the offenses were took place.
	
#### HOUR:
At what particular hour of the day the offense is recorded.
	
#### UCR_PART: They haven't mentioned anything particular or important related to the dataset with the UCR_PART.
	
#### STREET:
Offenses are recorded in which street of that are area the offense took place.

#### Lat: 
Latitude of that location.
	
#### Long: 
Longitude of that location.

#### Location: Which consists of both longitude and latitude coordinates of the location.

### Data Cleanup
•	This dataset is having some non-significant columns which have no information in it and neither required for the future analysis part. So, we are removing those columns.

•	We removed OFFENSE_CODE_GROUP because the whole column consists of null values it will not be useful for the future analysis parts. 'Lat', 'Long', 'Location' columns are not going to give any useful analysis according to the prediction which I needed.

•	UCR_PART this whole column consists of the null values.
    
### Exploratory data analysis

•	Now coming to the EDA part, we are performing distribution on the columns which are having some interesting characteristics shown up.

•	HOUR vs OFFENSE DESCRIPTION
Most of the offenses are took place in the '0' & '17' hours in the midnight and Evening respectively..

•	DISTRICT vs OFFENSE DESCRIPTION
Conidering the 'DISTRICT' & 'OFFENSE_DESCRIPTION' in the dataset, most of the offenses are took place in the 'B2' District..

•	SHOOTING vs HOUR
Most of the shootings are took place in the 12:00 AM midnight.
To be precise at '0' Hours in the morning.
Shootings are less involved in the offenses and most of them were handeled without shooting.

### Modeling

.    	Categorizing the Target Variable into three classes to ease the regression models.

.       As mentioned Below a day is divided into three classes which are 'DAY', 'NIGHT' & 'MIDNIGHT'.

.       The main reason to consider 'NIGHT' & 'MIDNIGHT' are most of the crimes are happening in the time of 23 to 4 in the morning.


### Pipeline Construction & Feature Engineering
.       I've taken the classified columns and the numeric columns and turned them into pipelines one after another.
.       I utilized the 'median' imputing approach for numerical pipelines and the'most_frequent' method for categorical pipelines.
.       I've put them to use in the creation of a processing pipeline.

#### Splitting the Dataset
.      	By splitting the datasets into two categories testing & Training.
.      	Considering the 'HOUR' Column in the dataset, We have created a new column which is 'Time of day'.

#### Logistic Regression

.     	Constructing the pipeline for this particular model.
.      Using l2, None penalty methods in the params. Because L2 penalty function uses the sum of the squares of the parameters and Ridge Regression encourages this sum to be small

.      Grid search gives us the ability to search over specified values for each of the parameters listed above. We do this by passing GridSearchCV a dictionary with parameter names as keys, and lists of values to try as arguments for those parameters.

.      validation score is 53.90% & Test score is 53.81%
By performing hyperparameter searches, we will get the best values where the validations score are good to taken and implemented in secondary search results on the regression model.

.      After this we will get the classification reports of both Testing & training.
.      by performing ROC & area under curve on the regression model we got around 0.61 of AUC.

#### Decision Tree

.      Constructing the pipeline for this particular model.

.      Using custom model__max_depth and model__min_sample_split values, we will find the right parameters for better validation scores

.      Grid search gives us the ability to search over specified values for each of the parameters listed above. We do this by passing GridSearchCV a dictionary with parameter names as keys, and lists of values to try as arguments for those parameters.

.      validation score is 54.24% & Test score is 54.23%
By performing hyperparameter searches, we will get the best values where the validations score are good to taken and implemented in secondary search results on the regression model.

.      After this we will get the classification reports of both Testing & training. Accuracy is 65%

.      By performing ROC & area under curve on the regression model we got around 0.51 of AUC.

#### KNN Classifier

.      Constructing the pipeline for this particular model.

.      This model seems to be best for classification when hyperparameter number of neighbors are 60The accuracy of KNN classifier is 0.6480306727082608

.      Even after taking the closet values compared with the above value we are still getting the same value in params.

.      By performing ROC & area under curve on the regression model we got around 0.59 of AUC.

#### Conclusion

.      Considering the three machine learning models, the Decision tree model shows the highest accuracy even though compared with the remaining models they are similar in their accuracy. Accuracy can be increased by using better modeling techniques.
