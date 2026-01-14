# WEEK 6
## 1. Overview

"The objective of week 6 was to analyze and assess the behavior of operating systems under varying workloads." Using applications identified during week 3, performance was assessed under baseline, load, and optimized conditions. All testing was done remotely via SSH connection, and data was collected for comparison purposes.

Assessment Brief CMPN202 Operate

## 2. Testing Methodology
### Metrics Collected
The following variables were assessed when it was appropriate:
- CPU Usage and Load Average
- Memory Use and Swap Activity
- The amount of memory
- Disk Input/Output Throughput and Latency
- Network Throughput and Latency
- Service response times

### Testing Scenarios

For each application, the following steps were considered:
1. Baseline Testing - Server idle, no active workload
2. Load Testing: The application is run under a controlled load.
3. Bottleneck Identification – Analysis of constrained resources
4. Optimisation Testing – Configuration changes applied and re-tested

In this way, a structured format was used, which helped ensure a level of consistency when

## 3. Performance Results Summary

Observed Behavior

- CPU-bound workload (stress-ng
 There was high usage of the CPU and high values of the load average, which proved the scheduling of the CPUs as the bottleneck.

- Memory intensive workload (stress-ng
 There was an increase in the usage of RAM, with the swapping process being noticed when the system's memory pressure was raised.

- Disk I/O workload (fio)
 The disk latency increased considerably during the random write requests, which revealed the I/O wait as a bottleneck.

- Network workload (iperf3
m The throughput came very close to the virtual network capacity, with a moderate CPU overhead because of processing of packets.

- Server load (nginx)
 Low idle resource utilization, with CPU resource utilization increasing proportionally with network resource utilization under request load.

## 4. Performance Optimisation & Impact
There were two optimisations that were implemented.

Optimisation 1: Background Services Reduction

Useless services were disabled in order to free up CPU and memory resources.

Result:
- Lower baseline CPU utilization

- Enhanced response times when under load

Optimisation 2: Adjusted Application Load Parameters

The intensity of the workload was adjusted (for example, by reducing the number of workers or by varying the size of the I/O

Result:
- Reduce peak resource contention
- System stability under constant load conditions has also seen improvements.

The quantitative results illustrate improvement in performance with system stability.

## 5. Network Performance Analysis
Network latency and speed were tested using ping and iperf3.
Latency: Constant and low in the host-only network
Throughput: As expected for a virtualized network

This validates that the network was not a bottleneck with regards to the CPU and disk I/O bottleneck.

## 6. Visualisation and Evidence
Visualization helps with quantitative analysis, with obvious patterns emerging in terms of performance.

## 7. Reflection and Critical Analysis (Week 6)
Week 6 proved the reliance of operating system performance on the nature of the workload. CPU- and disk-intensive applications showed points of contention, although the performance on the network was quite consistent. Optimisation proved that sometimes even the smallest changes to the configuration result in visible improvements; however, this may come with some costs regarding the other factors.
