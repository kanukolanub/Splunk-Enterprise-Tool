# Splunk-Enterprise-Tool

## Overview

This repository contains exercises focused on using Splunk Enterprise platform tool for adding data, searching data, and creating simple dashboards.

## Basics of Splunk Enterprise Tool:
* Indexing - The process of transforming the data is called indexing. During indexing, the incoming data is processed to enable fast searching and analysis. The index is a flat file repository for the data.
* Events - The processed results are stored in the index as events. Events are stored in the index as a group of files that fall into two categories:
* Raw data - which is the data that you add to the Splunk deployment. The raw data is stored in a compressed format.
* Index files - which include some metadata files that point to the raw data.
* These files reside in sets of directories, called buckets, that are organized by age. By default, all of your data is put into a single, preconfigured index called **main**.

The Splunk platform accepts any type of data. In particular, it works with all IT streaming and historical data. 
* Source of Data - The source of the data can be event logs, web logs, live application logs, network feeds, system metrics, change monitoring, message queues, archive files, and so on.
* In general, data sources are grouped into the following categories - Files and Directories, Network events, IT Operations, Cloud services, Database services, Security services, Virtualization services,   
  Application servers, Windows sources, Other sources. 

## Projects

### 1. Uploading the data

This project covers how to upload data to Splunk Enterprise platform tool.

* Key Topics: adding data
* Tools: Splunk Enterprise platform tool.
* Data: Tutorial data

**NOTE** The tutorial data file is updated daily and contains events that are timestamped for the previous seven days. The tutorial data contains several types of information about the fictitious online store             Buttercup Games). The information includes access.log files, secure.log files, and vendor_sales.log files from mail servers and web accounts.

### 2. Using the Search Splunk App
This project covers how to use the Search app on Splunk Enterprise platform tool.

* Key Topics: searching data
* Tools: Splunk Enterprise platform tool.
* Data: Tutorial data 
