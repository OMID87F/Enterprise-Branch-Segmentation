# Enterprise Branch Segmentation
## Overview
This project simulates a small enterprise network with a strong focus on network segmentation, security, centralized logging, and operational best practices.

Unlike a basic routing lab, this project combines Cisco switching, MikroTik routing, and a Linux Syslog server to build a realistic enterprise environment where network services, access policies, and monitoring work together.

The objective was not only to configure the network, but also to design security policies, validate their behavior, and troubleshoot implementation issues encountered during development.


## Objectives
* Implement VLAN-based network segmentation.
* Configure Inter-VLAN Routing.
* Deploy centralized DHCP services.
* Secure network management services.
* Enforce firewall policies between VLANs.
* Restrict Internet access where appropriate.
* Deploy centralized Syslog logging.
* Practice troubleshooting and validation.



## Technologies Used
* Cisco IOS
* MikroTik RouterOS
* Linux (Lubuntu)
* rsyslog
* GNS3
* VLANs
* Inter-VLAN Routing
* DHCP
* NAT
* Firewall
* SSH
* Syslog
* Simple Queues


## Key Features
* VLAN segmentation for multiple departments.
* Inter-VLAN routing through MikroTik RouterOS.
* DHCP services with static reservation for the Syslog server.
* Stateful firewall policies controlling communication between VLANs.
* SSH-only remote management.
* Router service hardening.
* Internet access using Source NAT.
* Basic bandwidth management using Simple Queues.
* Centralized logging from Cisco and MikroTik devices to a Linux Syslog server.



## Repository Structure
```
README.md
Documentation.md
Topology.png
Sources/
```



## Validation
The implementation was verified by:
* Correct VLAN and trunk configuration.
* Successful Inter-VLAN routing.
* Secure SSH management.
* Internet connectivity through NAT.
* Firewall policy enforcement between VLANs.
* Successful Syslog collection from Cisco and MikroTik devices.
* End-to-end validation of the complete enterprise topology.



## Challenges
One of the primary challenges involved Cisco Port Security.

Due to a limitation in the Cisco vIOS-L2 image used within GNS3, switch interfaces did not transition to the required *static access* mode after being configured as access ports. As a result, Port Security commands were rejected even though the configuration procedure was correct.

After extensive testing and investigation, the issue was identified as a software limitation of the virtual image rather than a configuration mistake.

Another interesting challenge involved configuring the Linux Syslog server. Cisco and MikroTik generate Syslog messages differently, requiring separate filtering rules to properly organize incoming logs.


## Documentation
Detailed configuration steps, screenshots, validation results, troubleshooting notes, and implementation details are available in `Documentation.md`.
> **Note:** The detailed documentation is currently written in Persian (Farsi).



## Learning Outcomes
Through this project I gained hands-on experience with:
* Enterprise network design
* Network segmentation
* Firewall policy design
* Linux system administration
* Centralized Syslog deployment
* Cisco and MikroTik interoperability
* Service hardening
* Network validation
* Troubleshooting vendor-specific limitations
