# WEEK 2
## 1. Introduction
The emphasis for Week 2 is the development of the security baseline and the performance testing plan before the system hardening process and the deployment of the workloads. The reason for having such plans developed before the process is carried out is to ensure the systematic application of security controls and the reliability and repeatability of performance metrics obtained in the later weeks.
## 2. Performance testing Plan
### Objectives

The performance test plan has the following aims:

- Establish baseline system performance

- Evaluate the effect of various types of workloads on system resources.

- Locate Bottlenecks in a Loaded

- Assess the impact of security controls and optimisations on performance

### Remotely Monitoring Methodology

Performance will be remotely monitored from the workstation via SSH, as dictated by the administrative restrictions imposed by the coursework. Nothing graphical will be done on the server.

Monitoring will be carried out using standard Linux CLI utilities, including:
- top / htop – CPU and memory utilisation
- free -h – memory availability
- df -h and iostat – disk usage and I/O performance
- ip, ss, and ping – network activity and latency
- Custom scripts for automated data collection

### Testing Approach
Performance testing will follow a structured process:

1. Baseline Testing – Measure idle system performance
2. Load Testing – Run selected applications under controlled load
3. Bottleneck Identification – Analyse resource constraints
4. Optimisation Testing – Apply configuration changes and re-test
5. Comparison – Evaluate performance before and after optimisation
This approach ensures consistent, comparable data across all testing phases.
## 3. Security Configuration Checklist
The security baseline is intended to reduce the attack surface of the system as much as possible, while still being usable and performing well.
The security baseline is intended to reduce the attack surface of the system as much as possible, while still being usable and performing well.

### SSH Securing
- Turn off password authentication
- Require key-based authentication
- Limit SSH access to a certain IP of a workstation
- Use Non-root login with privilege escalation using sudo

### Firewall Setup
- Enable firewall by default.
- Deny all incoming traffic except for SSH traffic
- Limit the SSH service to a specific trusted IP address

### Mandatory Access Control
- Use AppArmor or SELinux
- Apply access controls at the application level
- Track and record access control breaches

### Automatic Updates
- Establish automatic security patching to ensure the operating system is up-to-date automatically.

 ### User Privilege Management
- Add an administrative user that does not run as root and requires the fewest possible privileges.
- Use the principle of least privilege and prevent root login access.

### Network Security
- Setup the server within the host-only network so that the server is isolated from the outside world.
- Limit your connectivity to the global internet, as well as monitoring open ports and connections.
- Track and record access control breaches

## 4. Threat Model
A threat model has been developed to identify the risks and describe ways to mitigate them.

### Threat 1: brute-force attacks on SSH
### Risk:
The attackers attempt to gain access by guessing SSH login details repeatedly.

### Mitigation
- No password authentications
- "Require SSH key-based authentication"
- Restrict SSH access by IP
- Use Fail2ban to prevent recurrent login attempts

### Threat 2: Privilege Escal
### Risk:
“A compromised user account could be employed for gaining root access.”

 ### Mitigation
- DontAllowRoot
- Use sudo for controlled privilege escalation
- Apply least-privilege permissions to all users
- Analyze server logs for suspicious patterns.

### Threat 3: Inadequate or Untested Software

### Risk:
Old packages may contain identified vulnerabilities, which can be exploited by attackers.

### Mitigation
- Activate Updates for Security Fixes
- Occasionally check installed packages
- Run security scanning with Lynis

### Threat 4: Misconfigured Services
### Risk:
Unnecessary or misconfigured services may expose additional attack surfaces.

### Mitigation:
- Minimise installed services
- Audit running services regularly
- Justify each active service during the security audit

### 5. Reflection and Learning (Week 2)

Week 2 underlined one simple fact: security and performance go in hand with the start, not as check boxes at the back of everything. And by setting a security baseline before diving in, we've seen how prevention measures such as SSH hardening, firewalls, and other controls can cut risk without dragging down performance.

Having a testing plan in advance allows later results to be more meaningful and comparable. This week furthered this view that good system administration is the art of balancing security, performance, and usability-a thread running through every professional effort in the field.
