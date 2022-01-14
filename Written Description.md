# Finding Top 10 Subway Stations for a Billboard Marketing Campaign

> Kyle Turner

## Abstract
The goal of my project was to give my client 'California Sober' a model of the top 10 NYC subway stations for ridership in Manhattan + Brooklyn. With the data that I provide 'California Sober' they will then be able to create a billboard marketing campaign for their new THC Infused Seltzer at each station recomended.
I worked with data from the [MTA Turnstile Data](http://web.mta.info/developers/turnstile.html). After some exploratory analysis I was able to refine a model that I could use visualize my findings.

## Design
My prediction for the analysis was that the peak travel time for most stations would be 4pm - 8pm (for the weekdays), when people are getting off work. This is an ideal timeframe to market a THC Infused Seltzer.
The weekends were dropped because I wanted to focuse on the work crowd; people who would see the billboards repeatedly. 

## Data
From the MTA Turnstile Data I used the 3 most recent months available. The categories of interest to me were 'Date', 'Time', 'Station', 'Entries' and 'Exits'. I used to data to get an overall view of ridership at each station instead of looking into each individual turnstile at each station. There were 379 stations in the DataFrame.

## Algorithms
1. Summary Stats - I started getting inference into the data using summary stats from SQLAlchemy and continued to pull summary stats throught my work flow using Pandas.
2. Data Cleaning - The data cleaning really started after my SQLAlchemy queries. 

3. EDA

## Tools

- Numpy, Pandas, and SQLAlchemy for data manipulation
- Matplotlib and Seaborn for plotting
- DateTime for manipulation of dates and time

## Communication

