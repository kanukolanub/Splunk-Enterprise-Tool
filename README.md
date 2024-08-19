# Splunk-Enterprise-Tool

## Overview

This repository contains exercises focused on using Splunk Enterprise platform tool for adding data, searching data, and creating simple dashboards.

## Basics of Splunk Enterprise Tool:
**Indexing** - The process of transforming the data is called indexing. During indexing, the incoming data is processed to enable fast searching and analysis. The index is a flat file repository for the data
**Events** - The processed results are stored in the index as events. Events are stored in the index as a group of files that fall into two categories:
**Raw data** - which is the data that you add to the Splunk deployment. The raw data is stored in a compressed format.
**Index files** - which include some metadata files that point to the raw data.

The Splunk platform accepts any type of data. In particular, it works with all IT streaming and historical data. 
**Source of Data** - The source of the data can be event logs, web logs, live application logs, network feeds, system metrics, change monitoring, message queues, archive files, and so on.
In general, data sources are grouped into the following categories - Files and Directories, Network events, IT Operations, Cloud services, Database services, Security services, Virtualization services, Application servers, Windows sources, Other sources. 

## Projects

### 1. [Analyzing HTTP Traffic with Wireshark](https://github.com/kanukoalanub/Wireshark-projects/blob/main/Project-1-Analyzing-HTTP-Traffic-with-Wireshark.md) 

This project covers how to capture and analyze HTTP traffic using Wireshark. And also setting up captures, filtering HTTP traffic, analyzing HTTP requests and responses, and extracting payload data.

* Key Topics: HTTP Traffic, Packet Analysis, Filtering, Payload Extraction
* Tools: Wireshark, Web Browser
