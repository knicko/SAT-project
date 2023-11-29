Problem Statement: My job is to identify which states have a decreasing average test score and how participation affects the decrease.

In my project, I decided to first import datasets SAT 2017, 2018, and 2019. I cleaned the data by converting percentage strings to floats and removing reading & math columns then merged them into one data_final dataset. 

From here I calculated the standard deviation and mean of the participation & total
This data alone showed me that as participation went up, average total went down.

Now, I began to look for trends in the data. I created a function to calculate rate of change. I applied datasets 2017 and 2019 to the function and found that the states that increased participation the most from 2017 to 2019 actually decreased in average total score.

Here it was time to visualize the data. I did the correlation heatmap but with only 2 variables, I couldn't get anywhere. I plotted the histogram with the average SAT scores for each year. The frequencies on these charts down shifted every year. But there are some outliers that show some states getting higher scores. Majority of the scores went down however. Then I plotted a boxplot that represents the average SAT score. This figure was not good at showcasing the score change in correlation to the participation rate. The scatter plot probably best represents what i'd like to convey. As participation goes up, average score goes down. A trend can be seen clearly on this chart. Lastly is a bar chart that shows the State vs. Rate of Change in Total Score percentage. This chart was really helpful in finding which states in particular have a declining score.

I wish I can go further on this and specify which states have a increasing score along with participation rate but I had problems with my dataset.

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**participation_roc**|*float*|SAT (2017, 2018, 2019) |The percentage of change in participation rate from years 2017 to 2019 per state (units 0.35 = 35% positive change; -0.09 = 9% negative change).| 
|**total_score_roc**|*float*|SAT (2017, 2018, 2019)|The percentage of change in total score per state from years 2017 to 2019 per state (units 0.35 = 35% positive change; -0.09 = 9% negative change).|
|**state**|*string*|SAT (2017, 2018, 2019)|The state which showcases participation rate and totals.| 
|**participation**|*float*|SAT (2017, 2018, 2019)|The rate of participation for all students in given state for the SAT (units percent 0.98 = 98%).| 
|**total**|*int*|SAT (2017, 2018, 2019)|The total average score for all students who took the SAT in given state (units 1030 = average score)| 

The summary of my analysis is that as states increase their participation, the scores actually get worse. The states that need to loosen up their participation policy in order to increase average state test scores are Colorado, Illionois, Oklahoma, Rhode Island, and West Virginia. They clearly have the highest decline in average total score. These states also coincidentally have a positive participation rate of change from 2017 to 2019. This can be found in "df_rate_changes.sort_values('total_score_roc')" I recommend these states tighten up on who can take the SAT and not waste paper. Whereas the only states with negative participation rates are actually performing exceptionally well in the SAT's.

sources:

https://stackoverflow.com/questions/31357611/format-y-axis-as-percent
https://stackoverflow.com/questions/34010205/adding-caption-below-x-axis-for-a-scatter-plot-using-matplotlib
https://stackoverflow.com/questions/24023927/computing-standard-deviation-without-packages-in-python
