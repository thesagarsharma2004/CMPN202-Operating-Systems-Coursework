# WEEK 5
## 1. Overview
In Week 5, it is intended to further enhance security by incorporating sophisticated controls. These include enforcing mandatory access control, beginning automated security updates, pursuing intrusion detection, as well as creating two scripts. These would check the implemented security configuration and another to compile performance statistics remotely.

## 2. Mandatory Access Control (AppArmor)
AppArmor is enabled by default on the Ubuntu Server, and the following command was used to test it:

sudo aa-status

At least one profile (for example, nginx) was set into enforce mode, which actively prevented unauthorized access. Enforce mode prevents processes from doing anything outside their policy, which can reduce the effects of a service being compromised.

## 3. Automatic Security Updates
The auto-update feature for security updates was enabled to make sure that any known vulnerabilities were patched.

sudo apt install unattended-upgrades

sudo dpkg-reconfigure -plow

Configuration files in /etc/apt/apt.conf.d/ verify the enablement and scheduling of unattended upgrades through system timers.

## 4. Intrusion Detection with fail2ban
The fail2ban tool had been installed and configured on the system to defend against brute-force attacks on the SSH service.
sudo apt-get install fail2ban
sudo systemctl enable fail2ban


sudo systemctl start fail2ban

sudo fail2ban-client status sshd

This feature can automatically block the IP addresses that fail authentication repeatedly.

## 5. Security Baseline Verification Script (security-baseline.sh)
A server-side script was developed for checking all the security controls in Weeks 4 & 5.

The script verifies:

SSH hardening
(password and root login disabled)

Status of Firewall

AppArmor status Automatic Updates configuration status of fail2ban service The script is fully commented and runs through SSH.

## 6. Remote Monitoring Script (monitor-server.sh)
A script was created on the workstation side to gather performance data from the server through SSH.

It encompasses:
- CPU usage
- Memory usage
- Disk space and I/O operations are two
- Network status

The outputs will be stored in log files that have time stamps, which will help in analyzing the performance in Week 6.

## 7. Reflection (Week 5)
Week 5 showed the benefits of automation for improving the reliability and professionalism of system management. Mandatory access control and fail2ban improve security with little performance overhead, and the scripts ensure that configurations can be checked for consistencies. The controls form a solid foundation for testing performance and security.
