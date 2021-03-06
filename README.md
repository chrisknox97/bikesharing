# NY Citibike with Tableau

## Overview of Analysis

### To determine the viability of implementing a bike-sharing program in Des Moines, Iowa by conducting an analysis using Tableau; filtering by user type, gender, weekday and hourly usage rates to create a coheshive ``story`` and buisness strategy for potential investors. 

## Results: Jupyter Notebook

### To conduct our analysis we relied on Citibike Rider Data for August 2019. While this data is useful in its initial form, the ``trip duration`` is listed as an ``int64``, when we need it as a ``datetime`` datatype. To convert this we used the following portion of code:

    citibike_df["tripduration"] =pd.to_datetime(citibike_df["tripduration"]. unit = "s")

### In addition, the file also assigned numerical values to ``Gender`` which had to be replaced with line strings based on their respective values. 

    citibike_df["gender"].replace([0,1,2].["Unknown", "Male", "Female"], inplace = True)
    
### Finally, we exported the file as a ``csv`` for use in ``Tableau`` while dropping our ``Index``.

    citibike_df.to_csv("NYC_Citibike_Challenge.csv", index = False)
     
### The Jupyter Notebook used to write this code can be found [here.](https://github.com/chrisknox97/bikesharing/blob/main/NYC_Citibike_Challenge.ipynb)    
  
## Results: Tableau

#### Next we used Tableau Visualization Software to Create Seven Visualizations To Help Us Understand and Analyze The Citibike Data. 

### Customer Type
                        
#### Our First Visualization Focused on the types of users Using Citibike's Bike-Sharing Program. By Creating a Pie Chart we were able to easily see that the vast majority of users were ``Subscribers`` (1,900,359) rather than ``Customers`` (443,865). 

![Deliverable1](https://github.com/chrisknox97/bikesharing/blob/main/PNGs/Customer%20Type.png)

### August Peak Hours

#### Our Second Visulaization sought to determine what times of the day featured Peak Ridership. Through the creation of a horizontal bar chart, we found that Citibike Usage was lowest during the first four hours of a given day. In addition, the program hit its first peak usage during the day's 8th hour, while hitting another peak in its 17th hour. Overall, the chart showed the usage was generally high throughout the day, with the only exception remaining its first four hours. 

![Deliverable2](https://github.com/chrisknox97/bikesharing/blob/main/PNGs/August%20Peak%20Hours.png)

### Checkout Times For Users

#### Our Third Visualization, a line chart, looked at how long a customer used a bike to reach their destination. It found that the average ``Trip Duration`` was only 5 minutes long, with steady declines in usage rates afterwards. Users whose trips lasted over 60 minutes were virtually nonexistent.

![Deliverable3](https://github.com/chrisknox97/bikesharing/blob/main/PNGs/Checkout%20Times%20For%20Users.png)

### Checkout Times By Gender

#### With such a stark decline in ridership after 5 minutes, we also wanted to determine if said decline was in any way dependent on gender. However, we found that gender did not play a role in ``Trip Duration`` as ``Male`` users' trips peaked at 5 minutes, while ``Female`` users' trips peaked at 6 minutes. 

![Deliverable4](https://github.com/chrisknox97/bikesharing/blob/main/PNGs/Checkout%20Times%20By%20Gender.png)

### Trips By Weekday Per Hour

#### Another area of interest was what role the time of day, and the day of the week itself, played in rider usage. As a result, we created a heatmap which showed that the heaviest usage of Citibikes during Weekdays (Monday-Thursday) occured around 8 AM and 5-6PM; persumably due to riders commuting to and from work. While on the weekends, (Friday-Sunday) there was a wider range of usage starting later in the day, This may be due to riders not having to wake up as early to get to work, and the added free time the weekend affords most users. 

![Deliverable5](https://github.com/chrisknox97/bikesharing/blob/main/PNGs/Trips%20By%20Weekday%20Per%20Hour.png)

### Trips By Gender (Weekday Per Hour)

#### For our sixth visualization, we again looked at whether gender played a role in the aformentined usage patterns. Ultimately we found that the high usage times remained consistent across both ``Male`` and ``Female`` riders. While, ``Unknown`` gender types did not necessarily follow these patterns, this could be attributed to its significantly lower sample size. 

![Deliverable6](https://github.com/chrisknox97/bikesharing/blob/main/PNGs/Trips%20by%20Gender%20(Weekday%20Per%20Hour).png)

### User Trips By Gender By Weekday

#### Our Last Visulaization created a heatmap that looked at both ``Gender`` and ``Weekday`` usage within the context of User Type. This heatmap found that both ``Male`` and ``Female`` Users used the bike-sharing program signifcantly more if they were a ``Subscriber`` rather than a ``Customer``. Again, the ``Unknown`` gender type did not necessarily follow this pattern, but this again could be attributed to its lower sample size. 

![Deliverable7](https://github.com/chrisknox97/bikesharing/blob/main/PNGs/User%20Trips%20By%20Gender%20By%20Weekday.png)

### Tableau Story

#### For future reference, this analysis is also listed in my Tableau ``Story`` found on my Tableau Public Dashboard. The Link to My Tableau Public Dashboard can be found [here.](https://public.tableau.com/app/profile/chris7026/viz/NYCCitibikes_16534370029480/NYCCitibikes)

## Summary

### Analysis

#### Looking at our Tableau Visualizations we can infer the following conclusions: 

* Men Tend to Use Citibike Bike-Sharing Programs Signifcantly More Than Women.
* During the Week, Ridership Is Greatest During Times That Correlate With Job Commutes.
* During the Weekend, Ridership Is Spread Out Amongst The Middle of the Day and Ridership Begins To Spike Later. 
* Gender Does Not Play a Significant Role in Ridership
* Trip Durations Peak at 5 Minutes and Decline Therafter Suggesting Most Users Use The Program For Short Distances. 
* The Majority of Users Are Subscribers Rather Than Customers
* Subscribers Are More Likely To Use Bike-Sharing During Peak Periods

### Additional Visualizations

#### While this is a good start for our analysis, there are additional visualizations we can create to further our research and understanding; a couple of potental charts can be found listed below. 

* A Line Chart Showing Checkout Times For Users Throughout The Year (To Show How Ridership Differs During The Seasons)
* A Pie Chart Showing The Proportion of Users' Age Ranges (To Compare Against the Average Age of a Given Region's Households)
