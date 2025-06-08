# Azure Phase 2 Infrastructure Lab Project (In Progress)

This is an ongoing lab where I’m building out infrastructure tasks aligned with real-world Azure admin responsibilities and AZ-104 objectives. I'm using this project to get
hands-on experience beyond theory — learning through trial, troubleshooting, and documentation.

## 🎯 Lab Goal

Simulate what a junior Azure Cloud Administrator might manage in a production environment by deploying, securing, monitoring, and cleaning up cloud infrastructure 
using the Azure portal and supporting tools.

---

## 📦 Lab Focus Areas (Learning in Progress)

Here’s what this phase will include as I complete each task and learn by doing:

### 1. Resource Group Setup
- [x] Created `RG-AZInfraPhase2`
- [x] Applied basic tags (`Owner`, `Project`)
- [x] Apply ReadOnly lock post-deployment

### 2. Virtual Machines
- [ ] Deploy 1 Windows VM in East US  
- [ ] Deploy 1 Linux VM in West US  
- [ ] Configure IIS and NGINX on each respectively  
- [ ] Secure login via RDP/SSH and NSG

### 3. Networking & Security
- [ ] Create custom NSG with restricted inbound rules  
- [ ] Attach NSG to VM network interfaces  
- [ ] Build one custom VNet with subnet

### 4. Storage & Backup
- [ ] Create storage account and tag it  
- [ ] Set up blob container for logs or backups  
- [ ] Manually simulate backup steps

### 5. Monitoring & Cost Management
- [ ] Configure a budget ($20 max)
- [ ] Set up alerts for CPU/disk usage
- [ ] Document alerts + metrics overview

### 6. Automation (Optional)
- [ ] Use Azure CLI or PowerShell for tagging or teardown  
- [ ] Store scripts in GitHub with notes on usage

### 7. Teardown
- [ ] Document steps to deallocate and delete resources  
- [ ] Track cost and reflect on credit usage

---

## 📁 File Structure (WIP)
/phase2/
├── README.md
├── setup-instructions.md
├── resource-group-setup.md
├── vm-deployment.md
├── nsg-and-network.md
├── monitoring-cost.md
├── cleanup-plan.md
└── screenshots/

---

## 💬 Reflections

So far, this phase is already helping me understand how infrastructure, cost, and access all come together in Azure. I'm documenting things I don't understand, asking for 
help, and learning from mistakes — just like in a real cloud role.

As I complete each task, I’ll update this README and commit detailed sub-pages with screenshots, configs, and lessons learned.

---

Stay tuned for progress updates — and feel free to explore the subfiles once they go live.
