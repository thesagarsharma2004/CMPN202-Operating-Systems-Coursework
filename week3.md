## WEEK 3
## 1. Objective
The aim for Week 3 is, thus, to select an application mix that puts various OS subsystems under load simultaneously. By doing so, we can then systematically study the effect of CPU scheduling, memory management, disk I/O, and networking in the OS on this application mix. Here, we aim to perform the experiments using both synthetic and real applications.

## 2. Application Selection Matrix
| Workload Type      | Application/Service      | Why chosen                                               | What it measures                                       |
| ------------------ | ------------------------ | -------------------------------------------------------- | ------------------------------------------------------ |
| CPU-intensive      | `stress-ng`              | Industry-standard CPU stress tool; easy to scale threads | CPU scheduling, utilisation, load averages, throttling |
| RAM-intensive      | `stress-ng` (vm workers) | Can allocate/dirty memory to test pressure               | Memory allocation, swapping, OOM behaviour             |
| Disk I/O-intensive | `fio`                    | Flexible read/write patterns; widely used benchmark      | Throughput, IOPS, latency, disk queue behaviour        |
| Network-intensive  | `iperf3`                 | Standard for bandwidth testing                           | Throughput, retransmissions, network stack impact      |
| Server application | `nginx`                  | Common lightweight web server                            | Service behaviour under request load, response times   |

This combination ensures coverage of all major resource types required by the assessment.

## 3. Installation Documentation (SSH-Based)
All applications were installed on the server remotely via SSH, ensuring compliance with administrative constraints.
 sudo apt update
 sudo apt -y upgrade
 sudo apt -y install stress-ng fio iperf3 nginx sysstat curl

Installation verification:
 stress-ng --version
 fio --version
 iperf3 --version
 nginx -v

## 4. Expected Resource Usage Profiles
CPU (stress-ng): Near-maximum CPU utilisation and increased load averages proportional to worker count
Memory (stress-ng): Increased RAM consumption and potential swap usage under pressure
Disk (fio): Elevated disk activity, increased I/O wait, and measurable latency
Network (iperf3): High throughput with increased CPU usage due to packet processing
Server (nginx): Low idle usage, rising CPU and network activity under request load.

## 5. Monitoring Strategy
Performance data will be collected from the workstation via SSH using command-line tools:
top – CPU utilisation and process behaviour
free -h – memory usage and availability
df -h and iostat – disk capacity and I/O performance
iperf3 and ping – network throughput and latency
curl – HTTP response time measurement for nginx

Outputs will be logged during baseline and load testing to support structured data tables and performance visualisations.

## 6. Reflection and Critical Insight
Week 3 drove home the importance of selecting workloads that provide isolation of specific parts of the operating system, yet still echo real server behavior. Synthetic benchmarking tools allow us to dial in resource utilization with precision, and nginx brings authentic service-level performance dynamics into play. By laying out expected resource profiles and how we'll monitor them upfront, we cut down on bias and make later performance analysis more trustworthy.
