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
