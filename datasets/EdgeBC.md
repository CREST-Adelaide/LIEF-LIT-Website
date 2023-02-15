---
layout: page
title: EdgeBC Dataset
subtitle: Dataset from field and lab-based experimentation
---

# Context

The primary purpose of the Adelaide IoT Testbed is enabling researchers to deploy ad-hoc IoT testkits and operate their workload (e.g., ML, data processing, blockchain) in both lab-based and real-world settings. The Edge BC dataset is an exemplary result of such studies. 

The Edge BC dataset contains a lab-based reproduction of a deployment of the IoT testbed hardware within a search and rescue exercise in 2019. The IoT testbed gathers observation data via wireless sensors and commits them to a blockchain that operates within the testbed infrastructure itself, providing information assurance and provenance to the sensor data. The goal of the research was to quantify the performance and resource consumption of such blockchain configuration. The performance metrics of the blockchain and the resource load of the underlying IoT infrastructure form the Edge BC dataset. 

# Experiment Design

![](/assets/img/EdgeBC-Implementation-Diagram.png)

The figure above provides a simplified deployment- and component-view of the deployed hardware. 

The hardware was arranged in three ways in the lab:
- Ideal: All hardware within the same room
- Obstructed: Devices are placed in different rooms, breaking their line-of-sight connectivity
- Open field: Devices are deployed in an outdoor environment, mimicking the field experimentation condition. 

The following types of workloads were applied:
- Mesh: mesh networking only
- Mesh + IoT: mesh networking + IoT data collection and exchange
- Mesh + Ethereum: mesh networking + Ethereum blockchain operation
- Mesh + IoT + Ethereum: mesh network + IoT data collection + Ethereum blockchain for recording IoT data

### Experimental procedure

```bash
|- For each physical arrangement in [ideal (in 1 room), indoor (different rooms), outdoor]
|		|- Update configs.yaml (physical_arrangement)
|		|- Run network_test.yaml playbook to:
|				+ Start measuring latency, jitter and package loss
|				+ Measure signal level from master to gateway
|				+ Measure maximum throughput
|		|- For each evaluation subject in [adhoc, adhoc_IoT, adhoc_PoA, adhoc_IoT_PoA]
|      	|- Update configs.yaml (evaluation_subject)
|      	|- For 3 times
|      			|- Run bootstrap.yaml playbook to:
|								+ Bootstrap iot-testbed infrastructure
|      					+ Measure iot-testbed load on gateway nodes
|      			|- Run terminate.yaml playbook after 10 minutes to:
|      					+ Terminate the experiment
|      					+ Backup recorded metrics data
|      	|- For 10 times
|      			|- Run bootstrap.yaml playbook
|      			|- Run terminate.yaml playbook after 5 minutes
|		|- Run backup_smokeping.yaml playbook to:
|				+ Stop measuring latency, jitter and package loss
|		
```

###  Variables
- total cpu time
- total disk read (bytes)
- total disk write (bytes)
- filesystem sizes (bytes)
- available system memory (bytes)
- total network receive (bytes)
- total network transmit (bytes)
- battery level of Raspberry Pi (percentage)

# Resources

- [GitHub Repository](https://github.com/CREST-Adelaide/LIEF-LIT-EdgeBC-Dataset)