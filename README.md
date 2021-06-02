# Excel Project: &nbsp;Kickstart My Chart

## Background

Over $2 billion has been raised using the massively successful crowdfunding service, Kickstarter, but not every project has found success. &nbsp;Of the more than 300,000 projects launched on Kickstarter, only a third have made it through the funding process with a positive outcome.

Getting funded on Kickstarter requires meeting or exceeding the project's initial goal, so many organizations spend months looking through past projects in an attempt to discover some trick for finding success. &nbsp;For this study, we will organize and analyze a database of 4,000 past projects in order to uncover any hidden trends.

## Steps

![Kickstarter Table](Images/FullTable.png)

Using the Excel table provided, we modified and analyzed the data of 4,000 past Kickstarter projects in an attempt to uncover some market trends.

* Used conditional formatting to fill each cell in the `state` column with a different color, depending on whether the associated campaign was successful, failed, or canceled, or is currently live.

  * Created a new column O called `Percent Funded` that uses a formula to uncover how much money a campaign made to reach its initial goal.

* Used conditional formatting to fill each cell in the `Percent Funded` column using a three-color scale. &nbsp;The scale starts at 0 with a dark shade of red, transitioning to green at 100, and blue at 200.

  * Created a new column P called `Average Donation` that uses a formula to uncover how much each backer for the project paid on average.

  * Created two new columns, one called `Category` at Q and another called `Sub-Category` at R, which use formulas to split the `Category and Sub-Category` column into two parts.

  ![Category Stats](Images/CategoryStats.png)

  * Created a new sheet with a PivotTable to analyze the initial worksheet to count how many campaigns were successful, failed, canceled, or are currently live per **category**.

  * Created a stacked column PivotChart that can be filtered by country based on the table created.

  ![Subcategory Stats](Images/SubcategoryStats.png)

  * Created a new sheet with a PivotTable that will analyze the initial sheet to count how many campaigns were successful, failed, or canceled, or are currently live per **sub-category**.

  * Created a stacked column PivotChart that can be filtered by country and parent-category based on the table created.

* The dates stored within the `deadline` and `launched_at` columns use Unix timestamps. &nbsp;Fortunately, [there is a formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) that can be used to convert these timestamps to a normal date.

  * Created a new column named `Date Created Conversion` that will use [this formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) to convert the data contained within `launched_at` into Excel's date format.

  * Created a new column named `Date Ended Conversion` that will use [this formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) to convert the data contained within `deadline` into Excel's date format.

  ![Outcomes Based on Launch Date](Images/LaunchDateOutcomes.png)

  * Created a new sheet with a PivotTable with a column of `state`, rows of `Date Created Conversion`, values based on the count of `state`, and filters based on `parent category` and `Years`.

  * Created a PivotChart line graph that visualizes this new table.

* Created a report in Microsoft Word and answered the following questions.

1. &nbsp;Given the provided data, what are three conclusions we can draw about Kickstarter campaigns?
2. &nbsp;What are some limitations of this dataset?
3. &nbsp;What are some other possible tables and/or graphs that we could create?

## Additional Analysis

* Created a new sheet with 8 columns:

  * `Goal`
  * `Number Successful`
  * `Number Failed`
  * `Number Canceled`
  * `Total Projects`
  * `Percentage Successful`
  * `Percentage Failed`
  * `Percentage Canceled`

* In the `Goal` column, created 12 rows with the following headers:

  * Less than 1,000
  * 1,000 to 4,999
  * 5,000 to 9,999
  * 10,000 to 14,999
  * 15,000 to 19,999
  * 20,000 to 24,999
  * 25,000 to 29,999
  * 30,000 to 34,999
  * 35,000 to 39,999
  * 40,000 to 44,999
  * 45,000 to 49,999
  * Greater than or equal to 50,000

  ![Goal Outcomes](Images/GoalOutcomes.png)

* Used the `COUNTIFS()` formula to count how many successful, failed, and canceled projects were created with goals within the ranges listed above. &nbsp;Populated the `Number Successful`, `Number Failed`, and `Number Canceled` columns with this data.

* Added up each of the values in the `Number Successful`, `Number Failed`, and `Number Canceled` columns to populate the `Total Projects` column. &nbsp;Then, using a mathematical formula, found the percentage of projects that were successful, failed, or canceled per goal range.

* Created a line chart that graphs the relationship between a goal's amount and its chances at success, failure, or cancellation.

## Additional Statistical Analysis

If one were to describe a successful crowdfunding campaign, most people would use the number of campaign backers as a metric of success. &nbsp;One of the most efficient ways that data scientists characterize a quantitative metric, such as the number of campaign backers, is by creating a summary statistics table.

* Created a new worksheet in your workbook, and created a column each for the number of backers of successful campaigns and unsuccessful campaigns.

  ![Images/backers01.png](Images/backers01.png)

* Used Excel to evaluate the following for successful campaigns, and then for unsuccessful campaigns:

  * The mean number of backers.

  * The median number of backers.

  * The minimum number of backers.

  * The maximum number of backers.

  * The variance of the number of backers.

  * The standard deviation of the number of backers.

* Used this data to determine whether the mean or the median summarizes the data more meaningfully.

* Used this data to determine if there is more variability with successful or unsuccessful campaigns. &nbsp;Does this make sense? &nbsp;Why or why not?

- - -