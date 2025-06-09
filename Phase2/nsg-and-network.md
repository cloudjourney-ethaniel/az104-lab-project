# NSG and Networking (Phase 2 Lab)

This file will document how I configure Azure networking components: virtual networks (VNets), subnets, and network security groups (NSGs). 
These tasks are part of simulating a junior cloud admin role and will be updated as I complete each step.

---

## 🔧 VNet + Subnet Setup Plan

| Component | Details           |
| --------- | ----------------- |
| VNet Name | VNET-InfraLab   |
| Subnet    | Subnet-InfraLab |
| Region    | Matches VM region |

* I plan to manually create the VNet via the Azure Portal
* Each VM (Windows and Linux) will be assigned to a subnet

---

## 🔐 NSG Rules (Initial Setup Plan)

I will create a single NSG and associate it with the subnets or directly with each VM’s NIC. These are the initial rules I plan to configure:

| Port | Protocol | Purpose        | Status |
| ---- | -------- | -------------- | ------ |
| 22   | TCP      | SSH to Linux   | To Do  |
| 3389 | TCP      | RDP to Windows | To Do  |

* Public IPs will be temporarily enabled for access
* I’ll limit inbound rules to only my current IP for safety

---

## 🔄 Tests I Plan to Run

* [ ] Test removing public access to validate private-only scenarios
* [ ] Apply separate NSGs to each VM for finer control
* [ ] Block open ports and test denied access behavior

---

## Status Summary

This file will be updated as I implement and verify each network configuration. Screenshots and results will be tracked in the screenshots/ folder once available.

---

Next: Begin actual work in `vm-deployment.md`.
