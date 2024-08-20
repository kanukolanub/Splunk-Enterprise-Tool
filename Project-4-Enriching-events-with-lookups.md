# Enriching events with lookups

## Introduction

In this project, we will learn how to upload a lookup table file, create a lookup definition, and create an automatic lookup on Splunk Enterprise platform.

## Lab Set-up and Tools

1. **Tool**: Splunk Enterprise v9.3.0

## Exercises

### Exercise 1: How to upload a lookup table file
**scenario**: The events used in this tutorial data contain fields with the product codes and product IDs. Those codes and IDs do not tell you much about the products themselves, such as the product names. Being able to display the actual product names in reports and dashboards is useful to anyone who reads those reports or dashboards. That is where lookup files come in.
Lookup files contain data that does not change very often. This can include information about customers, products, employees, equipment, and so forth. For this tutorial, you will use a CSV lookup file that contains product IDs, product names, regular prices, sales prices, and product codes.

#### Steps
1. To use a lookup table file, you must upload the file to your Splunk platform.
   In the Lookups manager, locate Lookup table files and click Add new.
   You use the Add new view to upload the CSV file that you want to use as a lookup table.
   ![image](https://github.com/user-attachments/assets/69a6b33d-73ec-4a22-9f64-8f87e9dbcad8)
2. The Destination app field specifies which app you want to upload the lookup table file to. To upload the file in the Search app, select search from the list if it is not already selected.
3. Under Upload a lookup file, click Choose File and browse for the prices.csv file.
4. Under Destination filename, type prices.csv.
   This is the name that you will use when you create a lookup definition.
5. Click Save.
   This uploads your lookup file to the Search app and displays the lookup table files list.
   ![image](https://github.com/user-attachments/assets/8db6772b-015c-48d0-bc98-2b3e3c5e9c1f)
6. Share the lookup table file
When you upload a lookup table file, the default sharing setting is **Private**. To use the file with other applications or with specific roles, you need to change the permissions to the file. For this tutorial, you are going to share the lookup table file with all applications.
In the **Lookup table files** list, locate the prices.csv file at the bottom of the **Path** list.
In the **Sharing** column, notice that prices.csv is listed as **Private**.
To share the lookup table file, click **Permissions**.
In the Permissions dialog box, under **Object should appear in**, select **All apps**.
![image](https://github.com/user-attachments/assets/74bab0d7-aa4f-46b2-9a8e-7413bb85da15)
7. Click Save.
The Sharing setting for the prices.csv lookup table is set to Global.
![image](https://github.com/user-attachments/assets/bc58d9b5-b720-4563-826a-f2f78000e6e3)
8. Add the field lookup definition
It is not sufficient to share the lookup table file with an application. You must define the information in the lookup table file and how that information relates to the fields in your events. This is called a **lookup definition**. In the Lookup table file dialog box, select **Lookups** in the breadcrumbs to return to the Lookups manager.
9. For Lookup definitions, click Add New.
The Add new lookups definitions page opens, where you define the field lookup.
10. For the Destination app setting, make sure it is set to search to add the lookup definition to the Search app.
11. For Name, type prices_lookup.
12. For Type, select File-based.
    A file-based lookup is typically a static table, such as a CSV file.
13. For Lookup file, select prices.csv, which is the name of the lookup table file that you created.
![image](https://github.com/user-attachments/assets/63b0bbaf-8633-40dd-be38-a6066ae9a9be)
