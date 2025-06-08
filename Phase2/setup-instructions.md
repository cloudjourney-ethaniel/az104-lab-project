# Setup Instructions (Phase 2 Lab)

These are the initial setup steps for the Azure Phase 2 Infrastructure Lab. This document outlines how I prepared the 
environment before deploying any core infrastructure components. All steps were completed using the Azure Portal.

---

## ✅ 1. Resource Group Creation

* Navigated to the **Resource groups** blade in Azure Portal
* Clicked **Create**
* Resource group name: RG-AZInfraPhase2
* Region: East US
* Tags added:

  * Owner = ethaniel
  * Project = Phase2InfraLab
  * Environment = lab

---

## ✅ 2. Subscription + Credit Info

* Trial subscription used: **Azure Free Trial (\$200 credit)**
* Confirmed usage alerts configured in Azure Cost Management
* Planned total lab spend: **\$20 max**

---

## 🔐 3. Permissions & Locking (Planned Later)

* No locks added during initial setup — will apply **ReadOnly lock** later to simulate governance
* RBAC role assignments not required for solo lab

---

## 📁 Next Steps

* Proceed to resource-group-setup.md to document tagging and policy prep
* Then begin actual VM deployment and network design

---

*This file will be updated as more pre-deployment config is added or adjusted.*
