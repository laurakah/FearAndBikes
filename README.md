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
In additon to altering the time period before and after a terrorism attack we decided to apply a filter to our selection to ignore any incidents happened in Northern Ireland. 
Based on the 'motive' and 'group name' columns of the terrorism attacks data set we assumed that the political tension in this region may cause a significant amount of locally restricted incidents. 
These incidents may probably not be as present to the general public in the city of London as incidents in the United Kingdom motivated by not as locally restricted reasons. Therefore these probably won't affect the public level of concern as much as terrorism attacks with motives different to the conflicts in Northern Ireland.  

### Conclusions



