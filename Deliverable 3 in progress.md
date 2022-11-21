# Kickstarting with Excel

## Overview of Project

Louise launched a Kickstarter campaign for her play and she wanted to know the outcomes of different campaigns. We were given an Excel spreadsheet with data from thousands of other Kickstarter campaigns. To help inform Louise about trends in the Kickstarter spreadsheet, we performed an analysis of all the campaign's data and looked into figures like launch dates and funding goals to observe how they may have contributed to the campaign outcomes. 
### Purpose

We analyzed Kickstarter campaigns and visualized their data to better communicate some key insights as to which campaign launch months and funding goal ranges may have contributed to a higher incidence and percentage of successful, failed, or canceled Kickstarter Campaigns.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

- Upon an initial look at the data, we could have looked at funding goals and funds pledged, the corresponding launch dates and project deadlines, or even the average donations. We decided to first help Louise by giving her insights into the outcomes of other campaigns based on the months in which they were launched. To visualize this relationship, we started with a pivot table of the entire Kickstarter worksheet data set. We then filtered the pivot table on the 'parent category' and 'years'. We put the 'outcomes' in the columns field and the 'months' in the rows field. Finally, a count of each outcomes statistic was created by putting the 'outcomes' into the value field. After creating the pivot table, we filtered the parent category for 'theater' and only selected column labels for 'successful', 'failed', and 'canceled' outcomes.

![PivotTable_Theater_Outcomes](https://github.com/willmino/kickstarter-analysis/blob/main/PivotTable_Theater_Outcomes.png)

- We then generated a corresponding line chart with markers called 'Theater_Outcomes_vs_Launch'. This chart had months, including data from all years, on the x-axis, and the total number of either 'successful', 'failed', or 'canceled' campaign outcomes per month on the y-axis. 

![Theatre_Outcomes_Based_on_Launch_date](https://github.com/willmino/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

- In the chart above, we can see the successful campaigns are represented by the blue line, the failed campaigns are in orange, and the canceled campaigns are in yellow. The most notable features of the data are a higher count of successful campaigns in the months between May to July. However, the rise of successful campaigns during these months is accompanied by a rise in failed campaigns. Still, we can see a greater rate of increase in successful campaigns in these months compared to the smaller increase in the count of failed campaigns. For example, the count of successful campaigns jumped from about 70 in April to about 110 in May. The count of failed campaigns increased from about 40 in April to about 50 in May. The successful campaign count increased by about 57% between April and May. The failed campaign counts increased by only 25% between April and May.  This was much lower of an increase compared to the change exhibited by the successful campaign counts. This information would later help us drive home some conclusions which we could relay to Louise.

### Analysis of Outcomes Based on Goals

- We also wanted to make suggestions for Louise by analyzing how funding goal ranges may have contributed to certain campaign outcomes. We performed this analysis by creating the following table below. First, the `=COUNTIFS()` function was used to scan columns of the Kickstarter worksheet to find specific counts of data which met certain criteria. For each funding goal range, the `=COUNTIFS()` function looked for data which met the funding goal range criteria, along with meeting the subcategory 'play' criteria, and the corresponding outcomes crtieria. We then used the `=SUM()` function to determine the total number of all outcomes for campaigns within the designated funding goal range. The percentage of 'successful', 'failed', and 'canceled' campaign outcomes out of total outcomes per funding goal range were determined as well. 

![Outcomes_v_Goals_Table](https://github.com/willmino/kickstarter-analysis/blob/main/Outcomes_v_Goals_Table.png)

- We then highlighted the 'Goal' column along with the three percentage columns we generated. The following line chart 'Outcomes_vs_Goals' was generated from this data set.

![Outcomes_vs_Goals](https://github.com/willmino/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

-The percentage of successful campaigns are represented by the blue line. The percentage of failed campaigns are represented by the orange line. The grey line represents the canceled campaigns. Notice that no Kickstarter campaigns for plays were canceled. Thus, the percentage successful line and the percentage failed line exhibit an inverse relationship. This makes sense because if 75% of campaigns are successful in the funding goal range of 'less than 1000', than all of the remaining campaigns make up the rest of the outcomes. This means 25% of the campaigns in this goal range ended up failing. We can see the blue line for successful campaigns goes down as the funding goal increases, until a certain point, and the orange line for failed campaigns exhibits a corresponding increase in percentage failed as the funding goal increases, also up until a certain point. Visually, these lines are mirror images of each other. For some reason, campaigns within the funding goal range of equal to or greater than 35000 and less than or equal to 44999 exhibited a higher percentage successful rate at about 66% when compared to the lower percentage failed rate at about 34%. We can draw on the patterns within this figure to also help inform Louise of potential recommended funding goals for future Kickstarter campaigns.



### Challenges and Difficulties Encountered

- Campaign launch dates and funding deadlines were reported in UNIX timestamp format. This format was not readily interpretable by humans. To overcome this issue we needed to perform extra manipulation of the data before it could be useful. Conversely, the uniformity of the UNIX time stamps allowed for a single Excel function to convert all the data into a readable format. In a real world setting, we could encounter a single Excel spreadsheet with thousands of dates formatted in a dozen different ways. This could be a lot more complex and confusing to process when compared to the simple experience we had in processing these UNIX timestamps with a single equation.
The formula used for this processing was:

        `=(((A2/60)/60)/24)+DATE(1970,1,1)`

    where 'A2' is cell location of the UNIX timestamp. This formula converted the seconds counted since January 1st, 1970, into days. We then took the days counted and added it to the date January 1st, 1970 to get the correct output for the dates associated with the Kickstarter campaigns. Finally, the data was set to the 'Short Date' format.  We could then easily plot the associated campaign launch dates to help construct the Theater_Outcomes_vs_Launch chart.

# Conclusion

### What are two conclusions you can draw about the Outcomes based on Launch Date?

- A higher number of successful Kickstarter play campaigns launched between the months of May and July. May had 111 succesful launches, followed by June with 100 succesful launches, and lastly July with 87 succesful launches. All other months had below 72 successful launches. The increased likelihood of campaign successes between May and July could be due to the available funds from tax returns which are generally paid out in mid to late April. We concluded that campaigns launched during these post tax-season months have a higher incidence of meeting their funding goals.

- December had 37 successful Kickstarter campaigns which was the lowest out of any month launch date. At least 54 successful campaigns were launched in all other months. Increased expenses from holiday travel, family meals, and gifts among the general population could impact the available funds people could allocate for donations to Kickstarter campaigns. Thus, we concluded that the reduced availability of funds could lead to a higher likelihood of Kickstarter failures if a campaign was launched during the holiday season in December.

### What can you conclude about Outcomes based on Goals Chart?

- Kickstarters with a funding goal of less than or equal to 14999 had at least a 54% success rate. Kickstarters with a funding goal range greater than or equal to 35000 but less than or equal to 44999 exhibited a 67% success rate. The above listed ranges had the highest success rates. Campaigns with all other funding goal ranges had less than a 50% success rate. We can generally conclude that campaigns with lower funding goals have a high likelihood of success. This could be that people may only feel inclined to donate when they believe a campaign can fulfill a realistic goal that is not too high. However, there is one exception to our conclusion. The sweet spot of successful campaigns with funding ranges between 35000 and 44999 suggests that campaigns with high production quality may be worth the additional funding as long as the campaign goal is not greater than 45000.

### What are some limitations of this dataset?

- The Theater Outcomes vs Launch chart was derived from a pivot table that used months from all available years. Since we did not filter for any particular year, the data set was limited because we could not make the same conclusions on campaigns launched in the same month but from different years. For example, if there was a heavy economic recession during one year compared to economic growth in another year, then a campaign failing in May 2008 might still have been highly successful in May 2017.

- Another limitation of this data set was the sample size. There were only 1369 Kickstarter plays available for our 'Theater Outcomes by Launch Date' analysis. Having a larger sample size will allow for the mean of all the samples to be closer to the mean of the total population. In this way, we can still take a sample representation of some of the data, such as only the Kickstarter play campaigns, and know that this sample mean and statistics will more accurately reflect the total population mean and statistics. We can then draw conclusions from the sample play Kickstarter set knowing that the same relevant conclusions could be drawn about other Kickstarter campaign categories for parameters like campaign launch date and funding goal ranges.

-The last limitation of the data set can be observed in the Outcomes_vs_Goals line chart. The x-axis values do not have a unit of currency. They neither denote dollars nor pounds nor any currency. This chart takes in data from all other countries so the figures for ammounts of funds raised are imbued by the relative values each currency can trade for the other. For example, Kickstarters for plays in Mexico with a funding goal of 20000 pesos may have a comparable purchasing power to a different campaign in the United States with a funding goal of $1000 USD. The lack of defined units of currency creates confusion among the funding goals between Kickstarter plays campaigns from different countries. In this way, we cannot readily tell if a play from Mexico with a goal of 20000 pesos has a comparable production quality to a play from the United States with a funding goal of $1000 USD. Thus, this may add confusion for Louise if she should try her luck at launching a Kickstarter campaign for her next play in another country.

### What are some other possible tables and/or graphs that we could create?

![Proportion_of_Outcomes_by_Launch_Date](https://github.com/willmino/kickstarter-analysis/blob/main/Proportion_of_Outcomes_by_Launch_Date.png)

- Another useful visualization is a stacked bar chart with months on the x-axis and the percentage of kickstarter campaign outcomes on the y axis. Instead of simply viewing the number of campaigns by outcome in a line chart, a stacked bar chart reveals proportions for each outcome in single bars per month. These proportions better visualize a likelihood for each outcome and can more immediately suggest someone to pick the launch month which has the more successful color in it, like blue in this case. Also, when viewing more complex data sets such as an x-axis including multiple months across different years, interpreting a bar chart will have a simpler appearance compared to observing multiple zig-zag shaped lines. In this chart, we can quickly observe every month has at least a 49% success rate for meeting the funding goal for kickstarter for a play. This suggests that no matter what funding goal range Louise has, she will have a 49% chance of having a succesful campaign. In this way, you can observe things like how the funding success rate of campaigns is higher in May at 67% compared to December's lowest success rate at 49%. This information is also helpful for Louise.

If Louise wants to launch a new and successful Kickstarter campaign for a play, we recommend she launch the campaign between May and July and set a funding goal of less than $1000.


