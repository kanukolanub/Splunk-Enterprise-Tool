# Creating Dashboard and Panels

Dashboards are views that are made up of panels. The panels can contain modules such as search boxes, fields, charts, tables, and lists. Dashboard panels are usually connected to reports.
After you create a search visualization or save a report, you can add it to a new or existing dashboard. There is also a Dashboard Editor that you can use to create and edit dashboards. The Dashboard Editor is useful when you have a set of saved reports that you want to quickly add to a dashboard.

## Introduction

In this project, we will learn how to save a search as a dashboard panel and add an input element to the dashboard on Splunk Enterprise platform.

## Lab Set-up and Tools

1. **Tool**: Splunk Enterprise v9.3.0

## Exercises

### Exercise 1: Create Dashboard and Panels

1. Start a new search.
2. Change the time range to Previous week.
3. Run the following search.
   sourcetype=access_* status=200 action=purchase | top categoryId
   This search returns events from web server access log files for successful (status=200) purchases. The top command automatically returns the count of purchases for each product and the     
   percent each product is of the total purchases.

![image](https://github.com/user-attachments/assets/a6308d21-da53-48bf-b2f6-bf31c553b3a2)
4. Click the Visualization tab. The displays shows a Line Chart.
5. Change the Line Chart to Pie Chart.
![image](https://github.com/user-attachments/assets/aa48e963-ff8a-4ed5-9462-d82907490783)
6. Click Save As and select Dashboard Panel.
7. Define a new dashboard and dashboard panel.
For Dashboard, click New.
For Dashboard Title, type Buttercup Games - Purchases.
The Dashboard ID field displays buttercup_games__purchases.
For Dashboard Description, type Reports on Buttercup Games purchases data.
For Dashboard Permissions, keep the default setting Private.
For Panel Title, type Top Purchases by Category.
For Panel Content, keep the setting for Pie Chart.
![image](https://github.com/user-attachments/assets/9364d3a8-3083-482b-b0da-e8bc5a462aaf)
8. Click Save.
9. In the confirmation dialog box, click View Dashboard.
![image](https://github.com/user-attachments/assets/80d998ff-3a38-41f6-a879-f76cd379f2af)
