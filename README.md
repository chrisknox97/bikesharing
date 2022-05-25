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

#### Customer Type

#### August Peak Hours

#### Checkout Times For Users

#### Checkout Times By Gender

#### Trips By Weekday Per Hour

#### Trips By Gender (Weekday Per Hour)

#### User Trips By Gender By Weekday

## Summary

