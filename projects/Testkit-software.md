---
layout: page
title: IoT Testbed Middleware
subtitle: Middleware for operating IoT testkits
---

# Context

The test kit software is a collection of micro-services operating on gateways and aggregators responsbile for the collection and transmission of sensor data. 

# Design

![](/assets/img/Testkit_software.png)

**Main technologies**
-   Programming language: Python3
-   Package solution: Docker image
-   Database: Redis, MySQL, SQLite, InfluxDB
-   Protocols: HTTP, MQTT

**Current features**
-   Allow connecting from Raspberry Pi to multiple SensorTag and retrieving 8 types of sensor data.
-   Allow developers to push dummy data for testing by using HTTP requests on IoT Service.
-   Allow users/application to interact with InfluxDB to get neccessary data
-   Monitor current status of sensor data on Raspberry Pi
-   Monitor docker statistics
-   Grafana configuration for retrieving data from InfluxDB and create proper visualizations. Instructions to create Alerts on Grafana and send messages to Slack or send emails to users.
-   A simple dashboard built on Python and Flask framework.

# Resource

- [Prototype code](https://github.com/CREST-Adelaide/LIEF-LIT-Middleware)