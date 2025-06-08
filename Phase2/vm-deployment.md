# VM Deployment Log (Phase 2 Lab)

This page documents my process for deploying and configuring the virtual machines for Phase 2. The goal is to create one Windows VM and one Linux VM, placed in separate regions and networks, and prepare them for real admin-level management tasks.

---

## ✅ Deployment Goals

| VM Type | Region  | OS                  | Purpose                   |
| ------- | ------- | ------------------- | ------------------------- |
| Windows | East US | Windows Server 2019 | Practice RDP, IIS setup   |
| Linux   | West US | Ubuntu LTS          | Practice SSH, NGINX setup |

Both are deployed using **Standard\_B1s** for cost-efficiency.

---

## 🛠 Deployment Progress

* [ ] Create separate VNets or subnets for isolation
* [ ] Deploy Windows VM (via Portal)
* [ ] Enable RDP, install IIS
* [ ] Deploy Linux VM (via Portal)
* [ ] Configure SSH access, install NGINX

---

## 🔐 Access and Networking Notes

* I plan to apply **NSGs** later for security testing
* Public IPs will be enabled temporarily for direct access during lab
* Will later test NSG rules for locking down remote access

---

## 🧪 Early Observations

* 
* 
* 

---

Next: Documenting the network and NSG config in nsg-and-network.md, once both VMs are confirmed reachable and stable.
