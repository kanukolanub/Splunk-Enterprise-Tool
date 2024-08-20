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

#### Steps

1. 


#### Expected Output

1.

### Exercise 4: use a subsearch.

#### Steps

1. 


#### Expected Output

1.


