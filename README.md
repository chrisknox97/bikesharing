# NY Citibike with Tableau

## Overview of Our Analysis

### To determine the viability of implementing a bike-sharing program in Des Moines, Iowa by conducting an analysis using Tableau; filtering by user type, gender, weekday and hourly usage rates to create a coheshive ``story`` and buisness strategy for potential investors. 

## Results

### Jupyter Notebook

#### To conduct our analysis we relied on Citibike Rider Data for August 2019. While this data is useful in its initial form, the ``trip duration`` is listed as an ``int64``, when we need it as a ``datetime`` datatype. To convert this we used the following portion of code:

    citibike_df["tripduration"] =pd.to_datetime(citibike_df["tripduration"]. unit = "s")

#### In addition, the file also assigned numerical values to ``Gender`` which had to be replaced with line strings based on their repective values. 

    citibike_df["gender"].replace([0,1,2].["Unknown", "Male", "Female"], inplace = True)
    
#### Finally, we exported the file as a ``csv`` for use in ``Tableau`` while dropping our ``Index``.

    citibike_df.to_csv("NYC_Citibike_Challenge.csv", index = False)
  
### Tableau

##### Next we used Tableau Visualization Software to Create Seven Visualizations To Help Us Understand and Analyze The Citibike Data. 

#### Customer Type

##### Our First Visualization Focused nn the types of users Using Citibike's Bike-Sharing Program. By Creating a Pie Chart we were able to easily see that the vast majority of users were ``Subscribers`` (1,900,359) rather than ``Customers`` (443,865). 

#### August Peak Hours

##### Our Second Visulaization sought to determine what times of the day featured Peak Ridership. Through the creation of a horizontal bar chart, we found that overage Citibike Usage was Lowest During the first four hours of a given day. In addition, the program hit its first peak usage during the day's 8th hour, while hitting another peak in its 17th hour. Overall, the chart showed the usage was genrally high throughout the day, with the only exception remaining its first four hours. 

#### Checkout Times For Users

##### Our Third Visualization, a line chart, looked at how long a customer used a bike to reach their destination. It found that the average ``Trip Duration`` was only 5 minutes long, with steady declines in usage rates afterwards. Users whose trips lasted over 60 minutes were virtually nonexistent,  

#### Checkout Times By Gender

##### With such a stark decline in ridership after 5 minutes, we also wanted to determine if said decline was in any way dependent on gender. However, we found that gender did not play a role in ``Trip Duration`` as ``Male`` users' trips peaked at 5 minutes, while ``Female`` users' trips peaked at 6 minutes. 

#### Trips By Weekday Per Hour

##### Another area of interest was what role the time of day, and the day of the week itself, played in rider usage. As a result, we created a heatmap which showed that the heaviest usage of Citibikes during Weekdays (Monday-Thursday) occured around 8 AM and 5-6PM; persumably due to riders commuting to and from work. While on the weekedns, (Friday-Sunday) there was a wider range of usage starting later in the day, This may be due toriders not having to wake up as early to get to work, and the added free time the weekend affords most users. 

#### Trips By Gender (Weekday Per Hour)

##### For our sixth visualization, we again looked at whether gender played a role in the aformentined usage patterns. Ultimately we found that the high usage times remained consistent across both ``Male`` and ``Female`` riders. While, ``Unknown`` gender types did not necessarily follow these patterns, this could be attributed to its significantly lower sample size. 

#### User Trips By Gender By Weekday


## Summary

