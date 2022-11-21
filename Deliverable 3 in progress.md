# Kickstarting with Excel

## Overview of Project

Louise launched a succesful Kickstarter campaign for her play and she wanted to know the outcomes of different campaigns. To help inform Louise, we performed an analysis of other campaign's launch dates and funding goals to observe how they may have influenced the campaign outcomes. 
### Purpose

We analyzed Kickstarter campaigns and visualized their data to better communicate some key insights as to which campaign launch months and funding goal ranges may have contributed to a higher incidence and percentage of successful, failed, or canceled Kickstarter Campaigns.
## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered
Campaign launch dates and funding deadlines were reported in UNIX time stamps. This format was not readily interpretable by humans. To overcome this issue we needed to perform extra manipulation of the data before it could be useful. Conversely, the uniformity of the UNIX time stamps allowed for a single Excel function to convert all the data into a readable format. In a real world setting, we could encounter dates with dozens of differing formats which could be a lot more complex and confusing compared to the simple experience we had in processing this data.



- What are two conclusions you can draw about the Outcomes based on Launch Date?

1. A higher number of successful kickstarter play campaigns launched between the months of May and July. May had 111 succesful launches, followed by June with 100 succesful launches, and lastly July with 87 succesful launches. All other months had below 72 successful launches. The increased likelihood of campaign successes between May and July could be due to the available funds from tax returns which are generally paid out in mid to late April.

2. December had 37 successful kickstarter campaigns which was the lowest out of any month launch date. At least 54 successful campaigns were launched in all other months. Increased expenses from holiday travel, famly meals, and gifts among the general population could impact the available funds people could allocate for donations to Kickstarter campaigns Thus, the reduced availability of funds could lead to a higher likelihood of kickstarter failures if a campaign is launched in December.

- What can you conclude about the Outcomes based on Goals?

Kickstarters with a funding goal of less than or equal to 14999 had at least a 54% success rate. Kickstarters with a funding goal range greater than or equal to 35000 but less than or equal to 44999 exhibited a 67% success rate. The above listed ranges had the highest success rates. Campaigns with all other funding goal ranges had less than a 50% success rate. This suggests that campaigns with lower funding goals have a high likelihood of success. This could be that people may only feel inclined to donate when they believe a campaign can fulfill a realistic goal that is not too high. However, the sweet spot of successful campaigns with funding ranges between 35000 and 44999 suggest that campaigns with high production quality may be worth the additional funding as long as the campaign goal is not greater than 45000.

- What are some limitations of this dataset?
The Theater Outcomes vs Launch chart is derived from a pivot table that uses months from all available years. Since we did not filter for any particular year, the data set is limited because we cannot make conclusions on Kickstarter campaigns launched in a given month from different years. For example, if there was heavy economic recession during one year versus economic growth in another year, a campaign failing in May 2008 could have been highly successful in May 2017.

Another limitation of this data set is the sample size. There are only 1369 kickstarter plays available for analysis. 

- What are some other possible tables and/or graphs that we could create?

Another useful visualization we could create is a stacked bar chart with months on the x-axis and the percentage of kickstarter campaign outcomes on the y axis. Instead of simply viewing the number of campaigns by outcome in a line chart, a stacked bar chart reveals proportions for each outcome in a single bar per month. The proportions better visualize a likelihood for each outcome and can more immediately suggest to someone to pick the launch date which has more successful color in it, like blue in this case. When viewing more complex data sets such as months spread across many years, interpreting a bar chart will have a simpler appearance compared to observing multiple zig-zag shaped lines.




