# WEEK 1 SYSTEM PLANNING AND INITIAL SETUP
## 1.Introduction
The aim of Week 1 is to design the overall architecture for the proposed system, choose an operating system for the development platform, and conduct an initial survey of the system resources by using Linux command-line utilities.
## 2.System Architecture design
### Architecture overview
The system is made up of two machines:

- Workstation – It is a computer that is used by the administrator to control the server from a remote location.

- Server - This is a headless Linux server that can only be accessed through SSH.

This design is more secure and is modeled after real-world server administration practices.
### Architecture Diagram
![System Architecture](Image/Architecture.png)
## 3.Operating System Selection
### Selected OS 
### Ubuntu Server 24.04 
 ### Explanation
Ubuntu Server 24.04 Long Term Support was chosen because of its stability, compatibility with critical security applications such as UFW, Fail2Ban, Lynis, and AppArmor, as well as its overall community support, which is fueled by its broad adoption within the corporate world.
## 4. Virtualisation & Network Configuration
### Virtualisation Platform
The Linux server environment was run on VirtualBox as a virtual machine.

Setup Network

- Network mode: NAT
- IP address: Assigned by DHCP
- Access method: SSH enabled

It enables internal communications to take place in a secure manner without directly exposing the server on the outside network.
## 5. Initial System Inspection (CLI Commands)
