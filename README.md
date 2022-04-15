
  
 
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

•	Earlier in the OFFENSE CODE distribution Graph we had seen a hike in one of the code and now with the help of OFFENSE DESCRIPTION graph we can name them and have a better understanding of the graph.

•	'Investigate Personal' is shown the highest Offense ever recorded according to the data.

•	Here we can get that which Districts have more number of offenses took place and 'B2' has the highest number when compared with other Districts Most of the offenses are recorded without shooting and only few are recorded with shooting and here '1' indicates Yes and '0' as No for the shooting. Here Months are taken according to the numbers and more number of offenses are were recorded in the months of '8, 10' and least number of Offenses are taken in the month of '2'.

•	As compared with the mean and median in the above analysis we get that Box plot shows some different picture we are taking 'OFFENSE DESCRIPTION' & 'HOUR' as the two main features and constructing boxplot for them. Analysis shows that the mostly the offenses are taking at 10 & 15 hours and only few offenses are taken place in irregular times.

