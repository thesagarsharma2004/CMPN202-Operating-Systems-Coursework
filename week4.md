# WEEK 4
## Overview
This week, I was able to get my server operational and establish the basic root level security measures. Administration was conducted from a distant location via an SSH connection from my desktop, meeting the coursework requirement. The main elements implemented were a secured SSH server with key authentication, a limiting firewall that restricts connections to my desktop via SSH, and root level administration via a sudo-enabled user account.
## 2. SSH Key-Based Authentication (Server Access Hardening)

### 3. Firewall Configuration (Allow SSH from One Workstation Only)
To reduce attack surface, the firewall was configured to block all inbound traffic except SSH from a single trusted workstation IP.

#### 3.1 Enable UFW and apply rules (on server)
sudo ufw default deny incoming

sudo ufw default allow outgoing

sudo ufw allow from WORKSTATION_IP to any port 22 proto tcp

sudo ufw enable

#### 3.2 Verify firewall ruleset (on server)
sudo ufw status verbose

sudo ufw status numbered

## 4. User and Privilege Management (Least Privilege)
To follow least-privilege best practice:

- Administrative work is done using adminuser (sudo group)
- Direct root login is disabled in SSH
- Elevated privileges are used only when necessary via sudo

Verification:
whoami

groups

sudo -l

## 5. Remote Administration Evidence (Commands Executed via SSH)
All configurations were executed through SSH from the workstation to the server. Example evidence commands used during administration:

ssh adminuser@SERVER_IP

sudo systemctl status ssh --no-pager

sudo ufw status verbose

ip addr

## 6. Configuration File Evidence (Before vs After)

The key configuration file modified was:

- /etc/ssh/sshd_config

## 7. Reflection
Week 4 demonstrated how quickly a vanilla server installation may be secured by a handful of strategic decisions. Key-based SSH authentication completely mitigates brute force attacks, and hardening the firewall to only trust a single workstation significantly limits the threat of malicious use and breaches. Requiring authentication as a non-root user increases trust and helps contain the consequence of stolen login passwords. This provides enhanced protection with almost no performance penalty and gives a great foundation for the next week’s progress in securing the server using scripts.
