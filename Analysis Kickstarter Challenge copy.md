
# Kickstarting with Excel

## Overview of Project


Louise’s play Fever came close to its fundraising goal in a short amount of time. Now, she wants to know how different campaigns fared in relation to their launch dates and their funding goals. In this project, using Kickstarter data, the campaign outcomes based on their launch dates and their funding goals are being analyzed and visualized.



First analysis is about the relation between the success of campaigns in the parent category theatre and the launch month visualized by a line graph. Second analysis is about the relation between the success of campaigns in subcategory plays with parent category ‘theatre’ and their funding goals visualized by an other line graph.

## Analysis and Challenges



### Analysis of Outcomes Based on Launch Date

In order to analyze outcomes based on the launch date a pivot table and a pivot chart based on that table were used. For the purpose of filtering data in the pivot table, two separate columns were created for ‘Subcategory’ and ‘Parent Category’. Launch date was given originally in the unix timestamps format so it was not readable and was therefore converted to day/month/year format by using the formula

> =(((J2/60)/60)/24)+DATE(1970,1,1)

And then the format was changed from General to date. ‘J’ in the above mentioned formula is the column titled ‘Launched_at’. The new column was titled ‘Date Created Conversion’. From this column, the ‘Year’ column was created by using the formula

> = YEAR(S2)

Where ’S’ is the column titled ‘Date Created Conversion’. 

After aligning the date, a pivot table and pivot chart were created in a separate sheet named ‘Theater Outcomes by Launch Date’ in the excel document ![Kickstarter_Challenge] (https://github.com/nisahahmed90/Challenge-1/blob/main/Kickstarter_Challenge.xlsx). The main findings can be seen in the table and line graph below:

![](https://github.com/nisahahmed90/Challenge-1/blob/main/Pivot%20Table.png)

In the table, it can be seen that in every month the number of successful campaigns is higher than that of failed campaigns. The number of successful campaigns are highest in the month of May followed by June and July. The number of successful campaigns is the same in Feb and April, the number of failed campaigns is lower in Feb compared to April. Therefore, Feb is a preferable month to launch a theater campaign. Similarly, between April and August, the number of successful campaigns is higher in August compared to April, but a lower number of failed campaigns in April makes it a more preferable month to launch a theater campaign. 

Below is the line graph visualizing the above mentioned information and trends. 

![](https://github.com/nisahahmed90/Challenge-1/blob/main/Theater_Outcomes_vs_Launch.png)

In summary, based on this data alone, Louise can be recommended to launch campaign in May. However, if that is not possible then the campaign can be launched in the months of June, July, Feb, April or August in that order. 

### Analysis of Outcomes Based on Goals

In order to analyze the outcomes based on the goals, the range of goals was divided into intervals as shown in the chart below. As mentioned in the earlier analysis, since the date did not have separate columns for subcategory, those were created. In this analysis, the separate dat on subcategory was required to be used in COUNTIFS formula. Four conditions are put in the COUNTIFS function to get the data in the table below. These conditions are: lower and upper bound of the internal in the column titled ‘Goals’; “successful” or “failed” or “canceled” in the column titled ‘Outcomes’; “plays” in the column titled ‘Subcategory’. With this formula the data computed in this table contains the number and percentages of successful, failed and canceled campaigns. This table can be found in the sheet named “Outcomes Based on Goals” in in the excel document ![Kickstarter_Challenge] (https://github.com/nisahahmed90/Challenge-1/blob/main/Kickstarter_Challenge.xlsx). 

![](https://github.com/nisahahmed90/Challenge-1/blob/main/Outcomes%20Percentages.png)

For visual representation, the above mentioned date has been captured in a line graph shown below:

![](https://github.com/nisahahmed90/Challenge-1/blob/main/Outcomes_vs_Goals.png)

Both the table and graph show that the percentage of successful campaigns is higher than the percentage of failed campaigns for amount of goals less than $15000. However, they are equivalent if the amount of goals is between $15000 and $19999. For amount of goals between $20000 and $34999 the probability of a campaign failing is higher than the probability of the campaign being successful. 

However, there seems to be a drastic increase in the percentage of successful campaigns between $35000 and $44999. For the last two intervals there is a drastic drop in percentage of successful campaigns making the percentage of failed campaigns the highest. 

Overall, there seems to be a decreasing trend in the column ‘Percentage Successful’. However, for the intervals that see a drastic increase might indicate presence of outliers in the dataset, which at the moment are not in the scope of the purpose of this analysis. 

According to this computed data, Louise can be suggested to arrange a campaign such that the amount of the gaol is not more than $15000. 

### Challenges and Difficulties Encountered

When I first had a look at the dataset, it was overwhelming with all different columns that had to be filtered to get the relevant data. The first challenge that I was faced with was the ‘launched at’ column which was in the unix timestamps format and had to be converted to a readable date format. The module did outline a way to change it to a date so that was helpful. 

The second challenge was the ‘COUNTIFS’ formula. It went wrong the first couple of times because I either missed a bracket or a complete condition. Once the formula was sorted I had to make sure while copying it to other columns for other outcomes I changed the required information to get correct computation. 

The last challenge was to write this analysis as this is the first time I am using the markdown format but the provided guide was helpful. 

## Results

### Conclusions for Outcomes based on Launch Date

As per the analysis of Outcomes based on Launch Date, it can be concluded that May is the best month to launch a campaign for theater. Even though, the number of successful campaigns is more than the number of failed campaigns through other months as well, it as wise to launch campaigns in the months of June, July, February, April and August compared to other remaining months. 

### Conclusion for Outcomes based on Goals

If we look at the analysis drawn from Outcomes based on Goals, it is evident that it would be the best to have an amount of goal less than $15000 as the percentage of successful campaigns is higher for those intervals. Although the percentage of successful campaigns is higher for the amount of goals between $35000 and $45000 but this does not fit the general trend. 

### Limitations and Recommendations

There could be a few different limitations of the dataset being used here. The very first being the reliability as it can have missing data or incorrect data entry due to human error. We do not know how many people were reached out during the campaign and what were the tools used. We know today, social media plays a huge role in success of any campaigns and this dataset does not account for the medium through which campaigns were launched. 

Another dimension missing from the dataset is the duration of the campaigns. This information can be found by adding a column for duration with the help of finding a difference between ‘deadline’ and ‘launched_at’ columns. As we used the intervals for goals, we can use intervals for duration to see how long did the successful campaigns run for versus the failed campaigns. Visually this data can be represented as a line graph as well. 

Also, for the unexpected increase for amount of goals between $35000 and $45000 we need to analyze the outliers in the dataset. For this purpose we will have to find the lower and upper quartile along with the inter quartile range. This will help us identify t number of outliers and represent this information in a box diagram as well. 

All in all, based on the analysis I have provided the conclusions above with a mention of recommendations to increase the scope of the analysis at hand. 











 

















































