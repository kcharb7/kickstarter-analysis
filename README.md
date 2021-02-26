# Kickstarting with Excel

## Overview of Project

### Purpose
Louise, a play writer, set a budget of $12,000 for her play Fever. Through fundraising, she was able to come close to her goal in a short amount of time. Louise has asked how other fundraising campaigns compared for their launch dates and funding goals. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
I began my analysis by first determining the year in which each campaign was launched. This was achieved by creating a new column within the Kickstarter spreadsheet labelled “Years”. Then, I clicked on the cell beneath (i.e., U2) and typed the function YEAR(S2), with S indicating the column containing data on the Date Created Conversion. I applied this formula to the remaining cells by clicking the new cell, U2, and double-clicking the bottom right corner of the cell once my cursor turned black. 
![Screenshot_Year](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Year.png)

Once the Years column was created I clicked the “Insert” tab and the option “Pivot Table” in the top left-hand corner. 
![Screenshot_Create_PivotTable](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Create_PivotTable.png)

A new window appeared, and I selected for the pivot table to be placed in a new worksheet. The new worksheet was renamed “Theater Outcomes by Launch Date”. Looking at the “PivotTable Fields” box on the right-hand side of the screen, the pivot table was filtered by “Parent Category” and “Years” by dragging each variable under the “Filters” heading. Outcomes were placed under the “Columns” heading as well as the “Values” heading. “Date Created Conversion” was placed under the “Rows” heading, which resulted in the listing of “Years2” and “Quarters” variables under “Rows” as well. These two variables were removed by dragging and dropping them to the left outside of the box. 
![Screenshot_Design_PivotTable](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Design_PivotTable.png)

Clicking the filter tab beside “Column Labels”, campaign outcomes were filtered to show only “successful”, “failed”, and “canceled” outcomes and placed in descending order. 
![Screenshot_Filter_Columns](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Filter_Columns.png)

The “Parent Category” was filtered to show only “theater” by clicking the drop arrow within the row for “Parent Category”. 
![Screenshot_PivotTable](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_PivotTable.png)

Within the “Insert” tab, a pivot chart was created by clicking the “Pivot Chart” option in the middle of the bar. 
![Screenshot_Create_PivotChart](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Create_PivotChart.png)

This created a bar graph which was then changed to a line chart by clicking the bar graph, the “Design” tab at the top, and “Change Chart Type”. A “Line with Markers” design was selected. A title was added to the graph by once again clicking the graph, the “Design” tab, followed by the “Add Chart Element” option in the top left corner, moving the cursor to “Chart Title”, and selecting “Centered Overlay”. The title was changed to “Theater Outcomes Based on Launch Date” and I saved the chart by right clicking the graph and selecting “Save Picture As..”.
![Screenshot_PivotChart](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_PivotChart.png)

#### Challenges and Difficulties Encountered

During this portion of the analyses I first calculated the “Year” column using the “Date Ended Conversion” and did not discover this error until the final chart was complete. Though, once I noticed this error I re-did the above steps using the correct “Date Created Conversion” column. Other potential challenges that could be encountered may be placing the “Outcomes” in the “Rows” field and the “Date Created Conversion” in the “Column” and “Values” fields when creating the pivot table, resulting in a vastly different pivot chart. Additionally using “Years” in the “Rows” field would have impacted the pivot chart. 

### Analysis of Outcomes Based on Goals
A new sheet was created by clicking the “+” sign at the bottom of the page. The new sheet was labelled “Outcomes Based on Goals”. Eight columns were created with the labels “Goal”, “Number Successful”, “Number Failed”, “Number Canceled”, “Total Projects”, “Percentage Successful”, “Percentage Failed”, and “Percentage Canceled”. Under the “Goal” column the following groups were listed: Less Than 1000, 1000 to 4999, 5000 to 9999, 10000 to 14999, 15000 to 19999, 20000 to 24999, 25000 to 29999, 30000 to 34999, 35000 to 39999, 35000 to 39999, 40000 to 44999, 45000 to 49999, and Greater Than 50000. 
![Screenshot_Create_Outcomes_Based_On_Goals](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Create_Outcomes_Based_On_Goals.png)

The “Number Successful” column was populated using the COUNTIFS() function. Specifically, for B2, the following function was used: 

=COUNTIFS(Kickstarter!F:F, "successful", Kickstarter!D:D, "<1000", Kickstarter!R:R, "plays")

![Screenshot_COUNTIFS](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_COUNTIFS.png)
 
Using data from the Kickstarter sheet, this equation filtered for “successful” campaigns from the “Outcomes” column (column F), fundraising goals less than $1000 from the “Goals” column, and “plays” from the “Subcategory” column within the Kickstater sheet. For the next cell, B3, within the “Outcomes Based on Goals” sheet the criteria for the “goal” category was changed to align with that listed within the row (1000 to 4999), changing “<1000” to “>=1000” and adding “Kickstarter!D:D, "<=4999"” to get the following function:

=COUNTIFS(Kickstarter!F:F, "successful", Kickstarter!D:D, ">=1000", Kickstarter!R:R, "plays", Kickstarter!D:D, "<=4999")

This function was used for the remainder of the “Number Successful” column, changing the values for the “Goals” column to reflect the different goal categories. This function was additionally used to populate the “Number Failed’” and “Number Canceled” columns, changing the filter for the “Outcomes” column to “failed” and “canceled”, respectively. 

The “Total Projects” column was populated using the SUM() function, adding up the values from number of successful, failed, and canceled projects for each row. 
![Screenshot_SUM](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_SUM.png)

To populate the “Percentage Successful” column, I created the percentage values by dividing the value in the “Number Successful” column by the value in the “Total Projects” column for each row.
![Screenshot_Create_Percentage](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Create_Percentage.png)

I then re-labeled the data to indicate it was a percentage. 
![Screenshot_Label_Percentage](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Label_Percentage.png)

I followed these same steps to populate the “Percentage Failed” and “Percentage Canceled” columns. Subsequently, I highlighted these three columns and clicked the “Insert” tab followed by the picture indicating a line graph. 
![Screenshot_Create_LineChart](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Create_LineChart.png)

I then edited the x-axis for this graph by right-clicking the graph and clicking “Select Data…”. Beside the “Horizontal (Category) axis labels” I selected the red arrow icon, highlighted the values under the “Goal column”, hit enter, and clicked “OK”. 
![Screenshot_Select_Data_Horizontal_Axis](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_Select_Data_Horizontal_Axis.png)

I renamed the title of the line chart to “Outcomes Based on Goal” and saved the chart by right clicking the graph and selecting “Save Picture As..”.
![Screenshot_LineChart](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Screenshot_LineChart.png)

#### Challenges and Difficulties Encountered
When trying to make the line chart I initially began by creating a pivot table and a pivot chart. However, this resulted in a chart that separated the percentages into categories and did not look as the module indicated it should. I tried changing the “Value” field to show counts instead of sums but this did not rectify the issue. I went back to my dataset and instead highlighted the data of interest and selected the option to create a line graph from there. This seemed to solve the issue and create the intended graph. 

When creating the percentages for each outcome, I initially used the ROUND() function (i.e., =ROUND(B2/E2*100,0). However, when I went to make the graph the y-axis of the line chart was not showing as percentages. I checked the label for the column and saw there was an option for percentage but when I clicked that it multiplied all my variables by 100. So, I changed my equations to include only the division portion of the function and then labeled each column as “Percentage” by selecting the percentage option from the dropdown menu on the toolbar. 

## Results
### Outcomes based on Launch Date
![Theater_Outcomes_vs_Launch](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

Looking at the line chart for the theater outcomes based on launch date it is apparent that the month of May launched the most successful theater campaigns, followed by June. Less campaigns were successful from September to January, with December having the least amount of successful campaigns. January, March, September, November, and December all had about the same number of failed campaigns. 

### Outcomes based on Goals
![Outcomes_vs_Goals](https://github.com/kcharb7/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

Analyses on outcomes based on goals shows that all plays with campaign goals between $45,000 to $49,999 failed, while the highest percentage of successful campaigns was for plays with campaign goals less than $1,000. 

### Limitations of this dataset
Within the dataset there were no plays that were canceled, hindering our ability to determine whether campaign goals affected plays being canceled. Furthermore, most campaigns had goals less than $15,000, thus impacting the interpretations for percentage successful, failed, or canceled. For instance, only 6 campaigns had goals between $35,000 and $39,999, of which 4 were successful and 2 failed, rendering a percentage successful of 67%. This could be interpreted to mean that most campaigns with this goal range could be successful, but a larger sample size may indicate otherwise. 

### Recommendations for additional tables and/or graphs
A bar graph with outcomes on the y-axis and country on the x-axis could be created to determine which countries had the most successful theater campaigns.
Another bar graph could be created with country as the row and amount pledged as the column to see which countries pledged the most.
Another bar graph could be created with country as the row and backers count as the column to see which countries have higher backers counts for theater campaigns. 
Finally, a bar graph with amount pledged on the y-axis and year on the x-axis could be created to show which years had the highest pledges.
