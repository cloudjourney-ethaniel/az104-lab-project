# Resource Group Usage Log (Phase 2 Lab)

This file tracks how I'm leveraging the resource group RG-AZInfraPhase2 throughout Phase 2 of my lab. Since the group was already created during setup, this doc will focus on how it's being actively used and
managed — not how it was created.

---

## Ongoing Use

* All resources for Phase 2 (VMs, networking, monitoring, and cleanup) are being deployed into this group.
* I’m using this as a central place to explore how tagging, governance, and cost tools operate in a real-world structure.

---

## Tag Refinement

I initially added four basic tags during creation. From this point, I’ll:

* Adjust or expand tags as the environment grows
* Check how tags affect billing visibility in Cost Management
* Note any issues Azure raises related to missing or inconsistent tags

---

## Governance Tracking

No locks are applied yet — that’s intentional. Once I’ve deployed key infrastructure:

* A **ReadOnly lock** will be applied to simulate restricted environments
* I’ll document what happens when I try to edit/delete locked resources

---

## Change Log

| Change                        | Date       | Notes                          |
| ----------------------------- | ---------- | ------------------------------ |
| Reviewed tags in portal       | 2025-06-08 | All tags present and accurate  |
| Cost breakdown for RG checked | 2025-06-08 | No alerts triggered yet        |
| Lock status                   | Pending    | Will apply after VM deployment |

---

Next task: Begin provisioning VMs and updating the vm-deployment.md file accordingly.
