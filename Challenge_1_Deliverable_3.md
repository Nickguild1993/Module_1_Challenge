# Kickstarting with Excel

## Overview of Project

### Purpose
The purpose of the project was to analyze how similar campaigns to Louise’s faired vis-à-vis their respective launch dates and fundraising goals.

## Analysis and Challenges
**Analysis for Deliverable Number One**For analysing the relationship between camapign outcomes (Successful, Failed, and canceled) and their launch dates, I used a pivot table to extract the variables I was looking for from the data set.  Once I had that information in a pivot table, I filtered the table by *parent category* (specifically looking at theater) and *year*.  That allowed me to look at the outcomes of campaigns over the year (grouped by month) that were of the same type as Louise's- theater.

### Analysis of Outcomes Based on Launch Date

For analysing the relationship between camapign outcomes (Successful, Failed, and canceled) and their launch dates, I used a pivot table to extract the variables I was looking for from the data set.  Once I had that information in a pivot table, I filtered the table by *parent category* (specifically looking at theater) and *year*.  That allowed me to look at the outcomes of campaigns over the year (grouped by month) that were of the same type as Louise's- theater.

### Analysis of Outcomes Based on Goals

For analysing the relaionship between campaign outcomes (again, Successful, Failed, and Canceled) and their fundraising goals, I used the countifs function to pull data from the data set based on set criteria and ranges.  Here is an example of the formula from the sheet I used to find the number of *successful* campaigns that had a goal between $1,000 and $4,999. Countifs=(Kickstarter!$D:$D,">=1000",Kickstarter!F:F,"Successful",Kickstarter!$D:$D,"<=4999",Kickstarter!$R:$R,"plays")  That formula used for the above mentioned criteria allowed me to isolate all *successful* campaigns that had a goal between *$1000 and $4999* from the main data set, so Louise will be able to break down similar campaigns to hers based on their goal amount and outcome.

### Challenges and Difficulties Encountered
An issue I encounters when working on the **Outcomes Based on Launch Date** deliverable was getting the grouping for the correct on the pivot table.  When I first made the pivot table, I had the data how I wanted it, but I couldn't figure out how to get the rows to display by month- they were still in the **Unix Timestamp** format. To fix that, I had to create a new column in the Kickstarter data set labeled *Date Created 1* which took the values from the *Launched_At* column plugged them into the formula *=(((J2/60)/60)/24)+DATE(1970,1,1)* where J2 is the first entry in the *Launched_At* column.  That allowed me to convert the timestamps to dates, which I could then group based on month in the pivot table.

One issue I had to overcome was figuring out the formulas for the **Outcomes Based on Goals** deliverable.  I struggled at first on how to write them so that the infromation from the main data set would be pulled correctly. Using the correct math operators was also something I glazed over when I finally figured out how to make the formula work. At first, my line chart wasn't right because I forgot to put the *=* in the ">=1000" and "<=4999" ranges which made the number of *successful* campaigns being pulled from the main data set incorrect, skewing my graph. Once I got the hang of writing out the formulas though, it was pretty easy to change them based on the goal parameters, definitetly a challenge at first though.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
