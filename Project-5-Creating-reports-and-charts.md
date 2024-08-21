# Creating reports and charts

## Introduction

In this project, we will learn how to save and share your searches and explores more detailed search examples on Splunk Enterprise platform.

## Lab Set-up and Tools

1. **Tool**: Splunk Enterprise v9.3.0

## Exercises

### Exercise 1: Save a search as a report
Reports are created whenever you save a search. After you create a report, you can do a lot with it.

1. Do a search using following query: sourcetype=access_* status=200 action=purchase [search sourcetype=access_* status=200 action=purchase | top limit=1 clientip | table clientip] | stats count AS "Total Purchased", dc(productId) AS "Total Products", values(productName) AS "Product Names" BY clientip | rename clientip AS "VIP Customer"
2. Above the Search bar, click Save as and select Report.
3. In the Save As Report dialog box for Title type VIP Customer.
4. For Description, type Buttercup Games most frequent shopper.
5. For Time Range Picker, click Yes.
When you include a Time range picker in a report, it gives you the option of running the report with a different time range.
6. Click Save.
A confirmation dialog box opens confirming that your report has been created. From this dialog box you can perform the following actions.
Continue Editing. To refine the search and report format.
Add to Dashboard. To add the report to a new or existing dashboard.
View. To view the report.
7. Click View.
The title and description that you specified appear at the top of the report. Time range picker is also included at the top of the report. If you specified some other time range for the search, that time range appears in the report.
![image](https://github.com/user-attachments/assets/e355b82c-4518-4b0a-a124-f03e8bb8bc60)

**Find and share reports**
You can access your reports using the App bar.
Click Reports to open the Reports page and view the list of reports.
![image](https://github.com/user-attachments/assets/388a7fa9-518e-416f-8231-22c13674ca95)
When you save a report, Sharing is set to Private. Only you can view and edit the report. You can allow other apps to view, edit, or both view and edit the report by changing the report permission.
For the VIP Customer report, under Actions click Edit.
Select Edit Permissions.
In the Edit Permissions dialog box, set Display For to App.
The display expands to show more settings.
For Everyone, mark the check box under Read.
This action gives everyone who has access to this app the permission to view the report.
Click Save.
The Reports page appears. The Sharing setting for the VIP Customer report now reads App instead of Private.
![image](https://github.com/user-attachments/assets/93f27b78-41cf-4e9c-864a-72919d5e04a6)


### Exercise 2: Create a basic chart
1. Start a new search.
2. Set the time range to **All time**.
3. Run the following search.
sourcetype=access_* status=200 | chart count AS views count(eval(action="addtocart")) AS addtocart count(eval(action="purchase")) AS purchases by productName | rename productName AS "Product Name", views AS "Views", addtocart AS "Adds to Cart", purchases AS "Purchases"

This search uses the chart command to count the number of events that are action=purchase and action=addtocart. The search then uses the rename command to rename the fields that appear in the results.

The chart command is a transforming command. The results of the search appear on the **Statistics** tab.
![image](https://github.com/user-attachments/assets/7ab8b858-d688-43de-88bf-186d2492ab0a)

Click the **Visualization** tab. The search results appear in a Pie chart.
Change the display to a **Column chart**.
![image](https://github.com/user-attachments/assets/ca970e14-e743-4c09-b7cc-238107fa29e2)

### Exercise 3: Create a report from a custom chart
1. Start a new search.
2. Change the time range to All time.
3. Run the following search.
   sourcetype=access_* | timechart count(eval(action="purchase")) by productName usenull=f useother=f
4. Click the Visualization tab.
5. Change the chart type to a Line chart.
6. Use the Format drop-down to format the X-Axis, Y-Axis, and Legend to produce the following chart.
![image](https://github.com/user-attachments/assets/f7535938-3f7e-4a2c-beb6-1725a18836d5)

![image](https://github.com/user-attachments/assets/94465ca1-14cf-4f40-928f-815bd9442ce8)
7. Click Save As and select Report.
a. In the Save Report As dialog box, for Title type Product Purchases over Time.
b. For Description, type The number of purchases for each product.
c. For Content, select the first option Line Chart and Statistics Table.
d. For Time Range Picker, keep the default setting Yes.
8. Click Save.
9. In the confirmation dialog box, click View to see the report.
![image](https://github.com/user-attachments/assets/8d24603a-98f3-4489-8837-6e51180386a9)

### Exercise 4: Create a report from a sparkline chart
1. Start a new search.
2. Set the time range to All time.
3. Run the following search.
   sourcetype=access_* status=200 action=purchase| chart sparkline(count) AS "Purchases Trend" count AS Total BY categoryId | rename categoryId AS Category
   This search uses the chart command to count the number of purchases by using action="purchase". The search specifies the purchases made for each product by using categoryId. The   
   difference is that the count of purchases is now an argument of the sparkline() function.
   ![image](https://github.com/user-attachments/assets/7b676c6b-ef52-4dcf-b9d3-c918f6a64386)
4. Click Save As and select Report.
5. In the Save Report As dialog box, for Title type Purchasing trends.
6. For Description, type Count of purchases with trends.
7. Click Save.
8. In the confirmation dialog box, click View. Your report should look like this.
   ![image](https://github.com/user-attachments/assets/5fed26d2-4f1a-4e23-862a-4be11fcc6af0)

