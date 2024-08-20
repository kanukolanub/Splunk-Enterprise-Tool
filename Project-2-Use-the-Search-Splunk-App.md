# Use the Search Splunk App

## Introduction

In this project, we will use tutorial data file to upload to Splunk Enterprise platform.

## Lab Set-up and Tools

1. **Tool**: Splunk Enterprise v9.3.0

## Exercises

### Exercise 1: search summary view

#### Steps

1. click the Splunk logo on the Splunk bar to go to Splunk Home.
2. From Splunk Home, click Search & Reporting in the Apps panel.

#### Expected Output

1. This opens the Search Summary view in the Search app.
![image](https://github.com/user-attachments/assets/46684a35-3fbf-4afc-80a8-6bba4b7d37c5)

![image](https://github.com/user-attachments/assets/45e08aac-7e94-4686-b56b-9bb2e4b4aa5e)

### Exercise 2: new search view

#### Steps

1. The New Search view opens after you run a search.

#### Expected Output

![image](https://github.com/user-attachments/assets/31a41826-29fa-48cf-948d-8cc33c7e4317)

![image](https://github.com/user-attachments/assets/2e4c11ad-89c9-4664-bee8-fc384ad973d3)


### Exercise 3: specifying time ranges.

#### Steps

1. The New Search view opens after you run a search.
2. **preset time ranges** - The time range picker has many preset time ranges that you can select from.
Click the time range picker to see a list of the time range options. The **Presets** option contains **Real-time, Relative**, and **Other** time ranges.
**Real-time searches** display a live, streaming view of events. You can specify a window over which to retrieve events.
**Historical searches** display events from the past. You can restrict your search by specifying a relative time range or a specific date and time range.
3. In the **Presets option** in the **Relative** list, click Last 30 days.
The number of events returned should be larger. You changed the time range from Last 24 hours to  Last 30 days.
4. **Custom time ranges** Use a custom time range when one of the preset time ranges is not precise enough for your search.
5. **Specify date and time ranges**
You can also use the **Date Range** and **Date & Time Range** options to specify a custom time range.
Use **Between** to specify that events must occur between an earliest and latest date.
Use **Before** to specify that events must occur before a date.
Use **Since** to specify that events must occur after a date.


#### Expected Output
**Preset time ranges**
1.The number of events returned should be larger. You changed the time range from Last 24 hours to  Last 30 days.
![image](https://github.com/user-attachments/assets/ede5bfe8-a336-49f0-80c9-6da314ff3c7b)
**Custom time ranges**
![image](https://github.com/user-attachments/assets/fc03c1a1-10e3-47e3-b453-6c0bd8a4d9c2)
**Specify date and time ranges**
![image](https://github.com/user-attachments/assets/c28b7414-d012-440c-9d6b-db417b880a97)




