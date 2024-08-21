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


### Exercise 2: Add the field lookup definition

#### Steps
1. It is not sufficient to share the lookup table file with an application. You must define the information in the lookup table file and how that information relates to the fields in your events. This is called a **lookup definition**. In the Lookup table file dialog box, select **Lookups** in the breadcrumbs to return to the Lookups manager.
2. For Lookup definitions, click Add New.
The Add new lookups definitions page opens, where you define the field lookup.
3. For the Destination app setting, make sure it is set to search to add the lookup definition to the Search app.
4. For Name, type prices_lookup.
5. For Type, select File-based.
    A file-based lookup is typically a static table, such as a CSV file.
6. For Lookup file, select prices.csv, which is the name of the lookup table file that you created.
![image](https://github.com/user-attachments/assets/63b0bbaf-8633-40dd-be38-a6066ae9a9be)
7. Leave the check boxes for **Configure time-based lookup** and **Advanced options** unchecked.
8. Click **Save**.
The **prices_lookup** is now defined as a **file-based lookup**.
![image](https://github.com/user-attachments/assets/84670476-4b76-452c-b31b-a98df583599b)
9. **Share the lookup definition with all apps**
Now that you have created the lookup definition, you need to specify in which apps you want to use the lookup table.
In the Lookup definitions list, for the prices_lookup, click **Permissions**.
In the Permissions dialog box, under **Object should appear** in, select **All apps**.
![image](https://github.com/user-attachments/assets/399d7dee-5ec6-4dfa-8e00-3600c8a5190a)
10. Click Save.
In the Lookup definitions page, prices_lookup now has Global permissions.
You can use this field lookup to add information from the lookup table file to your events. You use the field lookup by specifying the lookup command in a search. Or, you can set the field lookup to run automatically.
![image](https://github.com/user-attachments/assets/c41d08d4-0c0f-4a73-971b-82804e4d9170)


### Exercise 3: Make the lookup automatic

### Steps
Instead of using the lookup command in your search when you want to apply a field lookup to your events, you can set the lookup to run automatically.

In the Lookup table file dialog box, select Lookups in the breadcrumbs to return to the Lookups manager.
1. In the Lookups manager, for Automatic lookups, click Add New.
2. This takes you to the Add new automatic lookups view, where you configure the lookup to run automatically.
![image](https://github.com/user-attachments/assets/c218d77a-13ae-4e98-96e7-474ab603afbf)

3. For the **Destination app** setting, make sure it is set to search to add the automatic lookup to the **Search** app.
4. For **Name**, type autolookup_prices.
5. For **Lookup table**, select **prices_lookup**.
   The other options are lookup table files that come with the product.
6. For **Apply to**, the value **sourcetype** is already selected. For **named**, type access_combined_wcookie.
7. For **Lookup input fields**, type productId in both text boxes.
   The lookup input fields are the fields that the lookup table and the events have in common. The lookup input fields are used to associate, or link, the fields from the lookup table file with fields in your events.
   The first text box specifies the field name in the lookup table file.
   The second text box specifies the field name in your events.
   The lookup table file has a **productId** column that contains values that match the values in the **productId** field in the events.
8. For **Lookup output fields**, specify the names of the fields from the lookup table file that you want to add to your event data. You can specify different names.
   The lookup table file has several fields. You will specify two of the fields in the lookup table to appear in your events.
   In the first text box, type product_name. This is the field in the prices.csv file that contains the descriptive name for each productId.
   In the second text box, after the equal sign, type productName. This is the name of the field that will appear in your events for the descriptive name of the product.
   Click **Add another field** to add another field after the first one.
   Type price in the first text box. This is the field in the prices.csv file that contains the price for each productId. Let's use the same name for the field that will appear in your events. Type price in the second       text box.
9. Keep **Overwrite field values unchecked**.
   Click **Save**.
   The Automatic lookup view appears and the lookup that you configured, autolookup_prices, is in the list. The full name is access_combined_wcookie : **LOOKUP-autolookup_prices**.
   ![image](https://github.com/user-attachments/assets/a087ba21-116d-40bd-adb0-844a28d002c8)
   ![image](https://github.com/user-attachments/assets/69d5e208-0924-4a9b-8433-234a56072a10)

   ### Exercise 4: Search with field lookups

   Now that you have defined the prices_lookup, you can see the fields from that lookup in your search results.
   ### Steps
**Show the lookup fields in your search results**
Because the prices_lookup is an automatic lookup, the fields from the lookup table will automatically appear in your search results.

1. From the Automatic Lookups window, click the Apps menu in the Splunk bar.
2. Click Search & Reporting to return to the Search app.
3. Change the time range to All time.
4. Run the following search to locate all of the web access activity.
   sourcetype=access_*
5. Scroll through the list of Interesting Fields in the Fields sidebar, and find the price field.
   This field is added to your events from the automatic lookup you created.
6. Next to Selected, click Yes. This moves the prices field from the list of Interesting Fields to the list of Selected Fields in the Fields sidebar.
7. Close the dialog box.
8. Scroll through the list of Interesting Fields in the Fields sidebar, and find the productName field.
9. Click productName to open the summary dialog box for the field.
10. Next to Selected, click Yes.
11. Close the dialog box.
Both the price and the productName fields appear in the Selected Fields list and in the search results.
Notice that not every event shows the price and the productName fields.

![image](https://github.com/user-attachments/assets/f485288b-ff9d-4f28-bfcd-1258b9213e67)

   ### Exercise 5: Search with the new lookup fields
When you setup the automatic lookup, you specified that the productId field in your indexed events corresponds to the productId field in the prices.csv file.
When you run a search, the Splunk software uses that relationship to retrieve, or lookup, data from the prices.csv file.
This enables you to specify the productName and price fields in your search criteria. The product name and price information does not exist in your indexed fields. This information exists in the lookup file, prices.csv.

**Example: Display the product names and prices**
You can show a list of the Buttercup Games product names and the corresponding prices by using the stats command to output a table that lists the prices by product. The search also uses the AS keyword and the rename command.

Run the following search using the All time time range.
sourcetype=access_* |stats values(price) AS Price BY productName |rename productName AS "Product Name"

![image](https://github.com/user-attachments/assets/a920194d-ce0b-4e3a-94c5-4439ed3e4bf9)

**Example: Display the VIP client purchases**
In Part 4 of this tutorial about subsearches, you created the following search that returned the product IDs of the products that a VIP client purchased.
sourcetype=access_* status=200 action=purchase [search sourcetype=access_* status=200 action=purchase | top limit=1 clientip | table clientip] | stats count AS "Total Purchased", dc(productId) AS "Total Products", values(productId) AS "Product IDs" BY clientip | rename clientip AS "VIP Customer"

The results of that search are shown in the following image
![image](https://github.com/user-attachments/assets/16b670d6-cbbf-4a98-9fcf-02c4e5e03f1f)
The events return the product IDs because that is the only data in your events about the product. However, now that you have defined the automatic lookup, you can return the actual product names.

Make sure that the time range is set to All time.
Using the same search, change values(productId) to values(productName).
Run the search.
sourcetype=access_* status=200 action=purchase [search sourcetype=access_* status=200 action=purchase | top limit=1 clientip | table clientip] | stats count AS "Total Purchased", dc(productId) AS "Total Products", values(productName) AS "Product Names" BY clientip | rename clientip AS "VIP Customer"

The results, like the previous search, show the purchases by the VIP customer. However, the results are more meaningful because the product names, which are coming from the lookup table, appear instead of the more cryptic product IDs.
![image](https://github.com/user-attachments/assets/83405fab-a468-4512-a0e6-ccc59b01373f)
