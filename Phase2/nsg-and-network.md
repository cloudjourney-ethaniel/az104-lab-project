# NSG and Networking (Phase 2 Lab)

This document details how I configured Azure networking components during Phase 2 of my lab, including virtual networks (VNets), subnets, and network security groups (NSGs). This simulates a junior cloud administrator role and is updated as I implement each step.

---

## 🔧 VNet + Subnet Setup

| Component | Details                |
| --------- | ---------------------- |
| VNet Name | VNET-InfraLab          |
| Subnets   | Subnet-LinuxLab, Subnet-WinLab |
| Region    | East US (Windows VM), West US (Linux VM) |

- Created VNets and subnets manually via the Azure Portal.
- Assigned the Windows VM (`vm-win-east`) to `Subnet-WinLab` and the Linux VM (`vm-linux-west`) to `Subnet-LinuxLab`.
- Ensured subnet IP ranges and region alignments support VM deployment.

### Screenshots  
| Description               | Image                              |
|---------------------------|----------------------------------|
| VNet and Subnet Overview  | Screenshots/Virtualnetworkandsubnet.png) |

---

## 🔐 NSG Configuration and Rules

- Created a single NSG named `NSG-InfraLab`.
- Associated the NSG with the Linux VM subnet and the Windows VM’s NIC to control inbound traffic.
- Configured inbound security rules as follows:

| Port | Protocol | Purpose            | Source         | Status    |
| -----|----------|--------------------|----------------|-----------|
| 22   | TCP      | SSH to Linux VM    | My IP          | Applied   |
| 80   | TCP      | HTTP to both VMs   | Any            | Applied   |
| 3389 | TCP      | RDP to Windows VM  | My IP          | Applied   |

- Default inbound traffic is denied, ensuring secure access.
- Public IPs were temporarily enabled to facilitate access during deployment and testing.

### Screenshots  
### Screenshots  
| Description              | Image                             |
|--------------------------|---------------------------------|
| NSG Inbound Security Rules | Screenshots/nsg-inbound-rules.png |

---

## 🔄 Tests and Validation

- Verified SSH access to Linux VM on port 22 from my workstation.
- Verified RDP access to Windows VM on port 3389 from my workstation.
- Confirmed HTTP (port 80) access to IIS and NGINX welcome pages externally.
- Tested network security by temporarily removing HTTP rule and confirming access was blocked.
- Used Azure Network Watcher’s **IP Flow Verify** to validate NSG effectiveness.
- Overcame local ISP blocking of HTTP traffic by verifying access via VPN.

---

## Troubleshooting and Learnings

- Gained practical experience associating NSGs to NICs versus subnets and saw how it affects traffic flow.  
- Discovered that local ISP restrictions can block cloud service access; using a VPN was an effective workaround.  
- Developed familiarity with Azure Portal, CLI, and Network Watcher tools for troubleshooting networking issues.  
- Learned the importance of public IP assignment to NICs for external connectivity.  
- Recognize the need for further practice managing NSG priorities to confidently avoid rule conflicts.

---

## Status Summary

All planned NSG and networking configurations are complete and verified for both VMs. The environment is secured with restrictive inbound rules limiting access to necessary ports and trusted IPs. This file will continue to be updated as the lab evolves.

---

**Next steps:**  
Continue building out practice VM deployments until confident, then explore advanced Azure networking topics, while documenting progress in `vm-deployment.md`.
