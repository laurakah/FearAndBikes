# Fear & Bikes
A practice on data cleaning, curation and merging of datasets using Python, Pandas and NumPy.

## Working question and framing
We are interested in the possibility of statistical correlation between national terrorism attacks and the people's use of bike sharing systems. While we won't answer any scientific questions here, we made an approach to collect data regarding global terrorism and the use of bike sharing offers concentrating on the example of the United Kingdom.
We asked outselves whether national terrorism attacks would increase people's concern to an extend where it changes their behaviour regarding transportation and logistical choices.
In order to have consistant data we limited our bike sharing data to the city of London and the data regarding terrorism attacks to the United Kingdom.

## Working steps
### Data Cleaning
Since we were planning on merging different datasets into one data frame on the date column our goal was to bring all data sources to one date format and group the data with more than one row per day by day without distorting the information held by the non date columns.
We made sure all date columns are holding a datetime object.

### Merging
We merged a curated set of data regarding terrorism in the United Kingdom into a set of data regarding the use of bike sharing opportunities in the city of London on the date. The represented time spans were limited to the years of 2015 and 2016 for both data sets.
Our merged dataframe contains information about time, type, location, damage and perpetrator of terrorism attacks in the UK as well as information about the total count of individual uses of shared bikes per day in the city of London, the weather conditions for this day and information about whether the day has been on a weekend or during a holiday.

### Analysis
To see whether the amount of individual uses of shared bikes per day in the city of London decreases or increases after a terrorism attack in the United Kingdom we extracted time series from the merged data set holding the same amount of days before and after the incident as well as the corresponding shared bikes use count. We processed time series of different length between 3 and 14 days before and after the incident.
We then summed up all shared bike count values before the incident as well as the values after the incident for every given time series for every given terrorism attack during 2015/16 in the United Kingdom in order to compare the before count with the after count. 
We then calculated the mean difference between the count after the incident and the count before the incident across every time series.

#### Variations
1. In additon to altering the time period before and after a terrorism attack we decided to apply a filter to our selection to ignore any incidents happened in Northern Ireland. 
Based on the 'motive' and 'group name' columns of the terrorism attacks data set we assumed that the political tension in this region may cause a significant amount of locally restricted incidents. 
These incidents may probably not be as present to the general public in the city of London as incidents in the United Kingdom motivated by not as locally restricted reasons. Therefore these probably won't affect the public level of concern as much as terrorism attacks with motives different to the conflicts in Northern Ireland.  
2. Since we assumed a possible influence of the weather conditions on people's use of bike sharing opportunities we tried to calculate a factor representing the likelyhood to go by shared bike depending on the mean bike rent counts per weather condition. We then applied this factor to the single bike rent count values in our time series to try to minimize the influence of the weather conditions on the outcome. 

### Conclusions
We did not expect to be able to make any scientific statements based on our data sources and analysis. 
While comparing the mean difference between the bike rent counts before and after an incident for different amount of days we were not able to find a pattern or a sign of possible correlation between national terrorism attacks and people's use of bike sharing opportunities. This either may be because there is no statistical correlation between these two factors or because our data sets were too small/not representative or our analysis approach did not match the use case.
Nevertheless we would like to continue our analysis and expand on our data sources and tools.

### Further Investigation
To be able to make scientifically and statitically stable statements about a possible correlation between national terrorism attacks and the likelyhood to use bike sharing opportunities we would like to expand the data we build our analysis on: examining data from different years than 2015/16 would be useful as well as expanding our analysis to other cities and countries. 
Also the sources of bike sharing data can be expanded by taking into account other bike sharing providers.
On the way to a solid theses we would like to minimize other possible factors influencing the use of bike sharing opportunities e.g. holiday, weekends, area, demographics, wealth, public transportation infrastructure, etc.
In the next step we want to investigate how different types of terrorism attacks reflect in the analysis: e.g. do incidents with a high number of victims have a higher impact on the use of bike sharing opportunities as ones with less/no victims? Does the target of an attack (e.g. private vs. public buildings, single/multiple persons, police, public transportation) reflect in the bike sharing rent counts somehow? And does the weapon type matter in terms of a possible correlation?
In a last step the analysis could be expanded to other kinds of transportation e.g. private bike, private cars or car sharing, etc.

### Data Sources
* [Data set on Bike Sharing in London](https://www.kaggle.com/hmavrodiev/london-bike-sharing-dataset)
* [The Global Terrorism Database](https://www.start.umd.edu/gtd/)

### Other Resources
* [Documentation of the complete Global Terrorism Database](https://www.start.umd.edu/gtd/downloads/Codebook.pdf)
* [Additional Data on Bike Sharing in the City of London](https://bikeshare-research.org/#apireq)


