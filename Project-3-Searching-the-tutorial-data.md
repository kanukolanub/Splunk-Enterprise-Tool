# Searching the tutorial data

## Introduction

In this project, we will learn how to use the Search app on Splunk Enterprise platform.

## Lab Set-up and Tools

1. **Tool**: Splunk Enterprise v9.3.0

## Exercises

### Exercise 1: basic searches and search results

#### Steps

1. We create searches that retrieve events from the index.
   **Note** - The data for this tutorial is for the Buttercup Games online store. The store sells games and other related items, such as t-shirts. In this     
   tutorial, you will primarily search the Apache web access logs, and correlate the access logs with the vendor sales logs.
2. **Using the Search Assistant**
The Search Assistant is a feature in the Search app that appears as you type your search criteria. The Search Assistant is like autocomplete, but so much more.
Click Search in the App bar to start a new search.
Type buttercup in the Search bar.
When you type a few letters into the Search bar, the Search Assistant shows you terms in your data that match the letters that you type in.
3. Click Search in the App bar to start a new search.
Type category in the Search bar. The **terms** that you see are in the tutorial data.
4. Select "categoryid=sports" from the Search Assistant list.
Press Enter, or click the Search icon on the right side of the Search bar, to run the search.
5. **Retreiving events from the index** - To retrieve events that mention errors or failures, you type the keywords in your search criteria. If you use multiple keywords, you must specify Boolean operators such as AND, OR, and NOT.
The AND operator is implied when you type in multiple keywords.
For example, typing buttercupgames error is the same as typing buttercupgames AND error.
Notice that you must capitalize Boolean operators. The asterisk ( * ) character is used as a wildcard character to match fail, failure, failed, failing, and so forth. When evaluating Boolean expressions, precedence is given to terms inside parentheses. NOT clauses are evaluated before OR clauses. AND clauses have the lowest precedence.
6. **change the display of event viewer**- Select the List option and click Table.
The display changes to show the event information column, the timestamp column, and columns for each of the Selected fields. You will learn more about the Selected fields later in the tutorial.
Change the display back to List.
   
#### Expected Output
using the search assistant
1. ![image](https://github.com/user-attachments/assets/8d2139b9-271b-4ea0-bccc-3a7d22215753)
Type category in the Search bar. The **terms** that you see are in the tutorial data.
![image](https://github.com/user-attachments/assets/7137d2dd-2098-448c-884f-f449dda47731)
Select "categoryid=sports" from the Search Assistant list.
![image](https://github.com/user-attachments/assets/76879412-8a44-4d71-bb11-a6a97c2a2316)
retreive events that mention errors or failure
![image](https://github.com/user-attachments/assets/d2754e42-5f20-4c72-b391-dc3fbde38809)
change the display of event viewer
![image](https://github.com/user-attachments/assets/4f03400f-4cf8-4cfa-af76-cab578ff76fa)


### Exercise 2: use fields to search

#### Steps

1. As events are retrieved that match your search, the Fields sidebar updates the **Selected Fields** and **Interesting Fields** lists. These are the fields that the Splunk software extracts from your data.
2. When you first run a search the **Selected Fields list** contains the default fields **host, source, and sourcetype**. These default fields appear in every event.
**Interesting Fields** are **fields that appear in at least 20% of the events**.

#### Expected Output

1.![image](https://github.com/user-attachments/assets/d5af0659-bab7-46db-a54f-a2699af8e2b8)
additional select fields can be selected from this window
![image](https://github.com/user-attachments/assets/d1d8eee6-52f1-44a9-8261-e520c234baab)


### Exercise 3: use the search language.

**scenario**: The searches that we run are retrieved events from your Splunk index. we were limited to asking questions that could only be answered by the number of events returned.
For example, you ran the following search to determine how many simulation games were purchased:
sourcetype=access_* status=200 action=purchase categoryId=simulation
To find this number for the days of the previous week, you need to run it against the data for each day of that week. To see which products are more popular than the other, run the search for each of the eight categoryId values and compare the results.

Splunk developed the Search Processing Language (SPL) to use with Splunk software. SPL encompasses all the search commands and their functions, arguments, and clauses. One way to learn the SPL language is by using the Search Assistant.


#### Steps

1. From the Account menu, select Preferences.
2. Click SPL Editor.
3. On the General tab next to Search assistant, click Full.
  The default setting is Compact. You can tell which mode is set by the dark gray background on the mode. The Full mode provides more information as you type commands in the Search bar.
4. Click Apply.
5. Click **Search** in the App bar to start a new search.
6. Change the time range to **All time**.
7. Type the letter **s** in the Search bar.
   The Search Assistant shows a list of **Matching Searches** and **Matching Terms**. It also explains briefly **How To Search**.
8. Select the following search from the Matching Searches list, or type the search into the Search bar.
   sourcetype=access_* status=200 action=purchase
9. After **action=purchase**, type a pipe character ( | ) into the Search bar.
   The pipe character indicates that you are about to use a command. The results of the search to the left of the pipe are used as the input to the command to the right of the pipe. You can pass the results of one   
   command into another command in a series, or **pipeline**, of search commands.
   Notice that the Search Assistant changes to show a list of **Common Next Commands**.
10. You want the search to return the most popular items bought at the Buttercup Games online store.
    Under Common Next Commands, select top.
    The top command is appended to your search string.
11. Type categoryId into the Search bar.
    The following search is the complete search string.
    sourcetype=access_* status=200 action=purchase | top categoryId
    The search criteria before the pipe character, sourcetype=access_* status=200 action=purchase, locates events from the access control log files, that were successful (HTTP status is 200), and that were a purchase of     a product.The search criteria after the pipe character, top categoryId, takes the events located and returns the categoryId field for the most common values.
12. Run the search.
    The results of the top command appear in the **Statistics** tab.
    **View results in the Statistics tab**
    The top command is a **transforming command**. Transforming commands organize the search results into a table. Use transforming commands to generate results that you can use to create visualizations such as column,      line, area, and pie charts. You will learn more about visualizations later in this tutorial.
    Because transforming commands return your search results in a table format, the results appear on the **Statistics** tab.
13. In this search for successful purchases, seven different category IDs were found. The list shows the category ID values from highest to lowest, based on the frequency of the category ID values in the events.
    Many of the transforming commands return additional fields that contain useful statistical information. The top command returns two new fields, count and percent.
    The count field specifies the number of times each value of the categoryId field occurs in the search results.
    The percent field specifies how large the count is compared to the total count.
14. **View and format results on the Visualization tab**
    You can also view the results of transforming searches on the **Visualization** tab, where you can format the chart type.
    Click the **Visualization** tab.
    By default, the **Visualization** tab opens with a Column chart.
    Click **Column Chart** to open the visualization type selector.
15. Column, Bar, and Pie charts are listed as the Recommended chart type for this data set.
    Select the Pie chart.
    Now, your visualization looks like the following pie chart.
16. Hover over each slice of the pie to see the count and percentage values for each categoryId.
17. Click on the STRATEGY slice.
    categoryId=STRATEGY is added to your search string, replacing the top command. The search runs again.

    
#### Expected Output

1. ![image](https://github.com/user-attachments/assets/871bd41b-6631-49e4-bcb0-35a38bef1342)
   ![image](https://github.com/user-attachments/assets/6ee45260-7bc9-4878-9129-9b92f403bc95)
   ![image](https://github.com/user-attachments/assets/d745ced6-7556-4e84-848c-e1d6be17df15)
   ![image](https://github.com/user-attachments/assets/9e3f0b58-7755-4e77-9024-346e29b19165)
   ![image](https://github.com/user-attachments/assets/65447464-8e5f-46ca-9386-e934721eaa66)
   ![image](https://github.com/user-attachments/assets/24fb826b-f50f-4b89-87a8-1b13b09fea3c)
   ![image](https://github.com/user-attachments/assets/c3f0dcfd-1fba-4248-b89e-507acbdc203b)
   ![image](https://github.com/user-attachments/assets/d9b9b85b-881f-40c1-8fbe-37bf4a9650c3)
   ![image](https://github.com/user-attachments/assets/644e6c18-8af9-43b0-bc30-625ff9d77352)
   ![image](https://github.com/user-attachments/assets/fd05ec2f-8ecb-463e-b096-7be4e0fcaa66)
   ![image](https://github.com/user-attachments/assets/befcfa19-3b96-4c91-b431-03e2d4fb1986)

### Exercise 4: use a subsearch.
**scenario**: We will learn how to correlate events by using subsearches.

**A subsearch is a search that is used to narrow down the set of events that you search on. 
The result of the subsearch is then used as an argument to the primary, or outer, search. Subsearches are enclosed in square brackets within a main search and are evaluated first.**

Let's find the single most frequent shopper on the Buttercup Games online store, and what that shopper has purchased.
The following examples show why a subsearch is useful. Example 1 shows how to find the most frequent shopper without a subsearch. Example 2 shows how to find the most frequent shopper with a subsearch.

**Example 1 shows how to find the most frequent shopper without a subsearch.**

#### Steps
You want to find the single most frequent shopper on the Buttercup Games online store and what that shopper has purchased. Use the top command to return the most frequent shopper.

1. Start a new search.
2. Change the time range to All time.
3. To find the shopper who accessed the online shop the most, use this search.
   sourcetype=access_* status=200 action=purchase | top limit=1 clientip
   The limit=1 argument specifies to return 1 value. The clientip argument specifies the field to return.
   ![image](https://github.com/user-attachments/assets/12e858db-e6c9-497f-8569-795acfcdcc8c)
   This search returns one clientip value, 87.194.216.51, which you will use to identify the VIP shopper. The search also returns a count and a percent.
   These are the default fields that are returned with the top command.
4. You now need to run another search to determine how many different products the VIP shopper has purchased. Use the stats command to count the purchases by this VIP customer.
   sourcetype=access_* status=200 action=purchase clientip=87.194.216.51 | stats count, distinct_count(productId), values(productId) by clientip
    This search uses several statistical functions with the stats command. An alias for the distinct_count() function is dc().
   ![image](https://github.com/user-attachments/assets/ac8524cf-5600-4199-b7f9-6cc604f7a82b)
   This search uses the count() function to return the total count of the purchases for the VIP shopper. The dc() function is the distinct_count function. Use this function to count the number of different, or unique,      products that the shopper bought. The values function is used to display the distinct product IDs as a multivalue field.
**   The drawback to this approach is that you have to run two searches each time you want to build this table. The top purchaser is not likely to be the same person in every time range **
