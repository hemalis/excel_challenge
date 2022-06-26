# Kickstarting with Excel

## Overview of Project

Project is to understand and analyze various campaigns' data to help Louise with his campaign for play "Fever".

### Purpose

Louise’s play Fever came close to its fundraising goal very soon. So, she wants to know how different campaigns in theater category are performing against their launch dates and their funding goals. So, the purpose of the analysis is to find and visualize campaign outcomes based on their launch dates and their funding goals that can help Louise to make informed decisions.

There are some good findings from the data, related to outcomes of the campaigns during specific time period of the year and based on their goal amounts. Based on these analysis Louise can take meaningful decision about her current and future campaigns.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

To do the analysis for outcomes bases on goal, I took following steps:

1. I converted "Date Created Converted" to "Years" Column as I wanted to do analysis at year level.

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal1/years.png?raw=true)

2. As I wanted to do analysis on Theater category, I created Pivot chart & I created both "Years" and "Parent Category" columns as filters. I filtered "Parent Category" to select "Theater".

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal1/theater.png)

3. As I wanted to analyze how many campaigns are in "success", "Failure" and "Canceled" categories for each month of the year, I took "outcomes" field in Columns & "Date Created" field in rows. I removed other date fields except month in rows as I wanted to analyze data at month level only.
4. I grabbed outcomes and put them as "Count of outcomes" in Values to analyze their counts per month.

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal1/pivot.png)


5. I filtered columns to just have required values of "success", "Failure" and "Canceled" and sorted it based on their outcome counts.

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal1/filter.png?raw=true)


6. To get more details about outcomes visually, I inserted Line chart for values in Pivot table. Also, to make it visually better, updated fonts and colors as well.

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal1/pivot%20output.png?raw=true)

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal1/chart.png?raw=true)


7. I analyzed data from the line chart and came to the results discussed in the section below. Chart is also uploaded for reference.

### Analysis of Outcomes Based on Goals

To analyze the outcomes based on the goals, I took following steps.

1. I created a column for different goals in ranges below: Less than 1000, 1000 to 4999, 5000 to 9999, 10000 to 14999, 15000 to 19999, 20000 to 24999, 25000 to 29999, 30000 to 34999, 35000 to 39999, 40000 to 44999, 45000 to 49999, and 50000 or More. This would help me understand how many campaigns were in each goal ranges and what outcomes came for those.

2. Using Countifs function I created columns for outcomes of "Successful", "Failed" and "Canceled" Category for each goal range and counted their numbers. This is done specifically for "Plays" category as Louise wanted to understand outcomes specifically for "Plays". One highly noticeable outcome was there were 0 canceled campaigns for each goal range.

- Here is one of the formulas I used for the same.

`=COUNTIFS(kickstarter!$D:$D,"<1000",kickstarter!$F:$F,"=successful",kickstarter!$R:$R,"=plays")`

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal2/total%20outcomes.png?raw=true)


3. Next step was to get percentage rate of successful, failed and canceled campaigns out of total campaigns in each goal range. This will help understand how outcome is fared against each other for each goal range. I converted data type for the "Percentage Successful", "Percentage Failed”, “Percentage Canceled" to percentage.

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal2/percentage%20outcomes.png?raw=true)

4. I created a line chart to see results visually and come up with some results which I described in results section below.

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal2/full%20table.png?raw=true)

![alt text](https://github.com/hemalis/excel_challenge/blob/main/resources/analysis_images/anal2/chart2.png?raw=true)


### Challenges and Difficulties Encountered

- I found it challenging to take "years" field for the analysis of "Outcomes based on Launch date" as it had to be converted from unix time in first place.
- Initially I found it challenging to use countifs and copy same formula for other categories due to dynamic values that were copied. I found a way to convert them in static and that made my analysis smoother.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

1. Campaigns in theater category which are launched in middle of the year (May-June-July) has higher rate of success. Although failure rates are on higher side in those months, there is a huge gap between success rate and failure rate. Middle of the year (specially May) is a best time for launching the campaigns in theater category.
2. In October, failure rate is high and success rate is not that good compared to other months. In January, there are highest cancelations. So, Louise should avoid launching campaigns in these months if possible.

- What can you conclude about the Outcomes based on Goals?

1. Campaigns in play category which has lower range of goal (0-$5000) has higher potential of success compared to campaigns with higher number of goals. There is an exception of campaigns in play category with goals between $35000-$45000 which has higher success rate but there are very a smaller number of campaigns to provide solid conclusion for those campaigns.

- What are some limitations of this dataset?

1. There aren't enough campaigns with higher amount of goals, which helps for decision making in that category.

2. There aren't any additional data attributes about outside factors that provides reasoning behind cancelations and failure of campaigns.

3. There isn't much information of marketing of campaigns & how it's conducted.
4. Max and min values pledged by backers in each campaign is not available that can provide more details about outliers within the campaign and distribution.

- What are some other possible tables and/or graphs that we could create?

1. We can create chart for analyzing data for each year level instead of overall months and that would give more details about some of the years which are contributing for success and failures.
2. We can do analysis for "US" only campaigns as Louise’s play is campaigned in "US". That would have provided more insights.
3. We could have taken "spotlight" field in account for this analysis by creating outcomes if they are in "spotlight" or not and see how it affects the results.
4. Analysis for "Outcomes based on Goal" can be performed on "Play" subcategory only instead of "Theater" as parent category which will be more specific to Loise's needs.
