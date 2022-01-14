# Finding Top 10 Subway Stations for a Billboard Marketing Campaign

> Kyle Turner

## Abstract
The goal of my project was to give my client 'California Sober' a model of the top 10 NYC subway stations for ridership in Manhattan and Brooklyn. With the data that I provide 'California Sober' they will be able to create a billboard marketing campaign for their new THC Infused Seltzer at each station recommended.

I worked with data from the [MTA Turnstile Data](http://web.mta.info/developers/turnstile.html). After some exploratory analysis I was able to refine a model that I could use visualize my findings.

## Design
My prediction for the analysis was that the peak travel time for most stations would be 4pm - 8pm (for the weekdays), when people are getting off work. This is an ideal timeframe to market a THC Infused Seltzer.
The weekends were dropped because I wanted to focus on the work crowd; people who would see the billboards repeatedly. 

## Data
From the MTA Turnstile Data I used the 3 most recent months available. The categories of interest to me were 'Date', 'Time', 'Station', 'Entries' and 'Exits'. I used to data to get an overall view of ridership at each station instead of looking into each individual turnstile at each station. There were 379 stations in the DataFrame.

## Algorithms
1. Summary Stats - I started getting inference into the data using summary stats from SQLAlchemy and continued to pull summary stats throught my work flow using Pandas.
2. Data Cleaning - The data cleaning really started after my SQLAlchemy queries. 
- created date_time column
- reformated using strip, lower, and replace('/','_')
- checked for and removed duplicates
- detect and drop Nulls
- dropped unnecessary columns
- all negative values for entries and exits were dropped from dataset since values should be accumulative
- renamed columns
- dropped outliers
3. EDA - To help with EDA I had to create a few new columns.
- time interval- to make sure all times were in 4hr intervals
- day of week
- entries differential- used a threshold based on the total seconds in a day. Assuming that each sec cannot have more than 1 person going through the turnstile at one time.
- exits differential- same threshold as above
- impression per 4hrs- created this as our ranking metric

During EDA I noticed 'DESC' had a unique vale (RECOVOR AUD) which seemed to be when the turnstiles were being reset. It was throwing of the data so I dropped it.
I also saw that half of the data was starting its time reading at 00:00:00 and the other half was shifted by 1hr starting at 01:00:00. Once I understood what was happening I was able to work with the data.

## Tools

- Numpy, Pandas, and SQLAlchemy for data manipulation
- Matplotlib and Seaborn for plotting
- DateTime for manipulation of dates and time

## Communication
Once I was able to model and plot the data my findings were as follows
- All top 10 stations for total ridership were in Manhattan and Brooklyn 
- The top station, 34 St-Penn Station, had over 9 million riders durring that time period
- The 10th top station, 125 St, had just under 5 million riders durring that time period
- Between the top 10 stations the top day of the week for total ridership in those 3 months was Wednesday
- Wednesday had just under 68 million riders and no other day was under 64 million riders
- For all days of the week the peak time for Impressions per Hour average was at 7pm
- The top 4 stations total Impressions per Hour happened between 6pm-7pm
- At 7pm, 34 St-Herald Sq, Impression per Hour peak around 750k 

### Cost for billboards (required minimum 4 weeks)
- Static subway-entrance ads- $3,000 per 4 week period
- Backlit Diorama Range of $400 - $1,950 per ad per 4 week period

- Static subway-entrance ads:  4 weeks $30,000 for 10 Stations
- Backlit Diorama- 4 weeks $4000 minimum for 10 Stations

My guidance to 'California Sober'- 
Focus the campaign on the top 10 stations, '34 ST-PENN STA', 'GRD CNTRL-42 ST', '86 ST', '34 ST-HERALD SQ', '14 ST-UNION SQ', '23 ST','FULTON ST', '125 ST', '42 ST-PORT AUTH', and 'TIMES SQ-42 ST'. Purchase at least 1 Static subway-entrance ad and Backlit Diorama for each of the top 10 stations. At each station the daily average potential impressions range between 550k-620k at 7pm weekdays.  The minimum cost will be for both will be $34,000 for 4 weeks. The Static subway-entrance ads will also have a lot of added impressions from sidewalk foot traffic. 'California Sober' can also couple this with a guerilla campaign of handing out drinks at the entrances of each station at the peak time, 7pm, to effectively reach the most people. If choosing one day to hand out drinks Wednesday is the top day for traffic.

### If I had more time for analysis
- I would break down the data to sation terminal
- Find the top 5 stations in Brooklyn
- I might also use data from the most recent year to 2 years
