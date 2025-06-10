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

* [x] Create separate VNets or subnets for isolation
      ![image](https://github.com/user-attachments/assets/edfcaa4d-cb2c-479d-a31e-27f6d3b1d4d7)

* [x] Deploy Windows VM (via Portal)
* [x] Enable RDP, install IIS
      ![IIS Page Desktop Proof](https://github.com/user-attachments/assets/dfe1fa7c-786c-44fc-aca9-79a44730f378)

* [x] Deploy Linux VM (via Portal)
* [x] Configure SSH access, install NGINX
      ![Nginx Page Desktop Proof](https://github.com/user-attachments/assets/50c31585-dbb1-4dda-aa3f-2e478a022bc3)

---

## 🔐 Access and Networking Notes

# Access and Networking Notes

## Windows VM (vm-win-east)

- Accessed the VM via **RDP** using the public IP assigned after resolving quota limits.
- Configured **Network Security Group (NSG)** to allow inbound **TCP port 80** for IIS HTTP traffic.
- Learned the importance of resizing the VM to meet IIS memory requirements.
- Cleaned up unused public IPs to resolve quota issues before successfully assigning a new one.
- Used PowerShell to reinstall IIS, resolving the initial service issues.

---

## Linux VM (vm-linux-west)

- Accessed the VM via **SSH** using the assigned public IP.
- Installed and configured **NGINX** to serve HTTP traffic.
- Created and attached a new public IP after deleting unused IPs to stay within quota.
- Configured NSG to allow inbound **TCP port 80** for HTTP access.
- Confirmed NGINX was running locally using `curl localhost` and verified external HTTP access.
- Encountered local ISP restrictions blocking HTTP traffic to the VM’s public IP.
  - Verified by successfully accessing the NGINX welcome page via **VPN** and mobile hotspot.
  - Learned to use VPN as a workaround for local network blocks.
- Used Ubuntu’s `service` command instead of `systemctl` to manage NGINX on Ubuntu 20.04 LTS.
- Confirmed no local firewall (`ufw`) was active on the VM, ruling out OS-level traffic blocking.

---

## Troubleshooting Takeaways

- Always verify that the NSG inbound rules have the correct priorities and no conflicting deny rules.
- Double-check the association of public IP addresses with the VM’s NIC.
- Use Azure Network Watcher’s **IP Flow Verify** to confirm if traffic is allowed or denied by NSGs.
- When experiencing timeout issues accessing VMs externally, test from different networks (mobile hotspot, VPN) to isolate ISP or local firewall blocks.
- Stopping a VM inside the OS does not deallocate it — use Azure Portal or CLI to properly stop and deallocate to avoid compute charges.



---

## 🧪 Early Observations


- Initial VM sizing (B1s) proved insufficient for IIS on Windows VM, necessitating an upgrade to B2s.
- Public IP quota limits required proactive cleanup of unused IPs before assigning new ones.
- Azure’s network configuration requires careful NSG setup tied directly to NIC or subnet for expected traffic flow.
- Familiarity with Linux service management commands (`service` vs `systemctl`) is crucial, as default instructions don’t always apply.
- Local ISP-level network restrictions can silently block inbound traffic, complicating external access verification.
- Diagnostic tools like Azure Network Watcher's IP Flow Verify provide critical insights beyond basic connectivity tests.


---

Next: Documenting the network and NSG config in nsg-and-network.md, once both VMs are confirmed reachable and stable.
