# Kickstarting with Excel

## Overview of Project

### Purpose
The purpose of the project was to analyze how similar campaigns to that of Louise’s faired vis-à-vis their respective launch dates and fundraising goals and how those variables affected their outcomes.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

For analysing the relationship between camapign outcomes (Successful, Failed, and Canceled) and their launch dates, I used a pivot table with the following fields: Filters were *Parent Category (Theater)* and *Years*, the column was *Outcomes*, the row was *Date Created* and the value was *Count of Outcomes*.  By filtering the data by the **theater** subcategory from the Parent Category, I was able to highlight campaigns that were of the same type as Louise's. Filtering by year (which I then grouped by month to further breakdown the distrubtion) allowed me to look at when campaigns were launched and the possible correlation that has to the outcome of said campaign. Because we only want to look at successful, failed, and canceled outcomes, I filtered out the *live* and *blank* values from the Outcomes column.  Below I've attached the pivot table used for the analysis.

![Alt text](https://github.com/Nickguild1993/Module_1_Challenge/blob/master/Outcomes_Vs_Goals_PIVOTTABLE.png)

### Analysis of Outcomes Based on Goals

For analysing the relaionship between campaign outcomes (Successful, Failed, and Canceled) and their fundraising goals, I used the **countifs formula** to pull data from the data set based on set criteria and ranges.  Here is an example of the formula from the sheet I used to find the number of *successful* campaigns that had a goal between $1,000 and $4,999. Countifs=(Kickstarter!$D:$D,">=1000",Kickstarter!F:F,"Successful",Kickstarter!$D:$D,"<=4999",Kickstarter!$R:$R,"plays")  That formula used for the above mentioned criteria allowed me to isolate all *successful* campaigns that had a goal between *$1000 and $4999* from the main data set, so Louise will be able to break down similar campaigns to hers based on their goal amount and subsequent outcome.  I repeated the formula for each range for all three outcomes, along with the total number of campaigns in each range.  Next, I wanted to look at the percentages for each outcome based on their fundraising range.  Doing so allowed me to more readily identify the breakdown of campaign outcomes based on their respective ranges.  Below I've attached the table used for the analysis.

![Alt Text](https://github.com/Nickguild1993/Module_1_Challenge/blob/master/Table%20of%20Outcomes%20vs%20Goals.png)

### Challenges and Difficulties Encountered
An issue I encountered when working on the **Outcomes Based on Launch Date** deliverable was getting the correct grouping (months) on the pivot table.  When I first made the pivot table, I had the data how I wanted it, but I couldn't figure out how to get the rows to display by month- they were still in the **Unix Timestamp** format. To fix that, I had to create a new column in the Kickstarter data set labeled *Date Created 1* which took the values from the *Launched_At* column and plugged them into the formula *=(((J2/60)/60)/24)+DATE(1970,1,1)* where J2 is the first entry in the *Launched_At* column.  That allowed me to convert the timestamps to dates, which I could then group based on month in the pivot table.

One issue I had to overcome was figuring out the formulas for the **Outcomes Based on Goals** deliverable.  I struggled at first with how to write them so that the infromation from the main data set would be pulled correctly. Specifically I had trouble with when to use " " for what I was looking to pull, and then making sure there weren't any errors in the formula, which happened a few times.  Using the correct math operators was then something I glazed over when I finally figured out how to make the formula work. At first, my line chart wasn't right because I forgot to put the *=* in both the ">=1000" and "<=4999" ranges which made the number of *successful* campaigns being pulled from the main data set incorrect, skewing my graph. Thankfully, I noticed that someone was off, and after some brief trouble shooting, realized my mistake. OVerall, once I got the hang of writing out the formulas, it was pretty easy to change them based on the goal parameters, however, it was a challenge for me at first.

## Results

### Conclusions drawn from the Outcomes based on Launch Date Analysis.

* The best time to launch a theater campaign kickstarter seems to be between the end of spring and beginning of summer. The peak month for successful campaigns is May, in which nearly 67% of the total campaigns launched were successful.
* The worst time to launch a theater campaign kickstarter was during the beginning of fall to the start of winter.  October and December were the worst during that timeframe, with failure rates of 43.48% and 46.67% respectively. 

### Conclusions drawn from Outcomes based on Goals Analysis.

* Campaigns that had a goal under $5,000 (made up of the two following ranges: <=$1,000 and >=$1,000 - <=$4,999)had the highest success rate by far, with over 72% of campaigns in that range being successful.  They are also the most heavily represented groupings, meaning that the data from those ranges (again, under $1,000 and $1,000-$4,999) are the most reliable to extrapolate from.  As the goal amount increased, the number of campaigns fitting those ranges decreased.

* Overall, the higher the campaign goal is, the less likely it is to be succesful.  However, it should be stated that this conclusion comes with two caveats. Firstly, this relationship isn't linear, and secondly, some of the higher ranges like the $35,000-$39,999 and $40,000-$44,9999 groups go against this conclusion. With that said, those specific ranges have such few *total* campaigns that fall within them, (6 and 3 campaigns, respectively) it is likely that if given more data points within those ranges the distribution of successes and failures would be smoothed out, leading to a result that is more in line with the other ranges- as campaign goal increases, success rate decreases.

### Limitations of the Dataset. 

* A litmitation for the **Outcomes based on Launch Date** analysis is that there isn't more specified grouping for the individual campaigns. You can see which months have the most successful campaigns, but we don't know when those campaigns start (beginning of the month, middle of the month, weekends, etc) and what the goal and pledged amounts were for each campaign.  Without that information, you have to be careful about what definitive conclusions you draw.  For example,  it's possible that a high percentage of the total campaigns started in May had a fundraising goal of under $5,000, when compared to other months, which would likely lead to a higher rate of  *successful* outcomes than you'd expect if the range of campaign goal amounts were evenly distributed for each month.  

* One limitation regarding the **Outcomes based on Goals** analysis is that there are very few data points for the larger *Goal* ranges.  Campaigns with goals over $25,000 are much less prevalent than campaigns with goals less than $25,000.  The limited sample size in that range causes the outcomes of those campaigns to less external validity because it's difficult to say if those results are outliers. For example, within the goal range of $45,000 - $49,999 we have one campaign that meets that criteria.  It's a campaign that failed, but does that mean that all campaigns that have a goal that falls within that range are destined to fail? That's very unlikely, but if you just looked at this dataset, one might think that if they don't consider the sample size. If we had a more equal frequency distrubtion of campaigns for each range, it would be much easier to be confident on drawing conclusions about the effect of *Goal Amount* vis-a-vis *Campaign Outcome*.

### Graphs and charts for further exploration of data.

* A bar chart would be helpful to visually breakdown the distribution of campaign outcomes based on their respective launch dates.
![Alt Text](https://github.com/Nickguild1993/Module_1_Challenge/blob/master/Theater_outcomes_Vs_LaunchBAR.png)

* A bar chart would also be useful to visualize the distribution of campaign outcomes based on their goals. The x-axis is the range of campaign fundraising goals, and the y-axis is the number of campaigns.
![alt text](https://github.com/Nickguild1993/Kickstarter-Analysis/blob/master/Outcomes_Vs_Goals_BAR.png)



