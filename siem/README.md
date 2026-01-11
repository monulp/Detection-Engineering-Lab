# SIEM Setup

## Overview
This section documents the setup of the SIEM platform used in this lab.
Splunk Enterprise was selected to mirror common SOC environments and to
support SPL-based detection engineering and alert development.

## SIEM Platform
- Product: Splunk Enterprise
- OS: Ubuntu Server 22.04 LTS
- Deployment Type: Single-instance (Search Head + Indexer)

## Virtual Machine Specifications
- Hypervisor: VirtualBox
- CPU: 2 cores
- Memory: 8 GB
- Disk: 50 GB (dynamic)
- Network: NAT (internal lab network)

## Installation Status
- [ ] OS installed
- [ ] SSH access enabled
- [ ] Splunk installed
- [ ] Web UI accessible
- [ ] Indexes created

## Notes
This lab intentionally uses a minimal single-instance Splunk deployment
to focus on detection engineering rather than infrastructure complexity.

# SIEM Setup (Splunk on Ubuntu Server)

## Purpose (Non-technical summary)
This SIEM host provides centralized log storage and search capability for the lab.
It is the platform where detections will run and investigations will be performed.

The goal of this phase was to deploy a stable, reproducible Splunk instance and
validate that it survives reboots, supports searching, and has adequate disk capacity.

---

## Platform Overview
- **SIEM:** Splunk Enterprise (single-instance)
- **OS:** Ubuntu Server 22.04 LTS
- **Hypervisor:** VirtualBox (Windows host)

---

## VM Specifications
- CPU: 4 vCPU
- RAM: 8 GB
- Disk: 80 GB (expanded using LVM after initial install)
- Network: Dual NIC
  - NAT (egress internet access)
  - Host-only (management/SSH from Windows host)

---

## Key Outcomes (Phase Completed)
✅ SSH access from Windows host works  
✅ Splunk Web UI reachable on port **8000**  
✅ Splunk running as a **systemd service** (boot persistence)  
✅ `_internal` search works (proof of indexing + search)  
✅ Disk expanded to satisfy Splunk minimum free space requirements  

---

## Access Details
- Splunk Web: `http://<HOST_ONLY_IP>:8000`
- SSH: `ssh splunk@<HOST_ONLY_IP>`

> Note: `<HOST_ONLY_IP>` is the VM's host-only interface IP (e.g., `192.168.56.x`).

---

## Validation Checks (Evidence)
### Network
```bash
ip a
ip route
```
## Splunk Service

```
sudo systemctl status splunk
/opt/splunk/bin/splunk version
```

## Splunk Functional Proof

In Splunk Search:

```
index=_internal | head 10
```
## Disk Capacity
```
df -h
lsblk
```
## Implementation Notes (What was learned)

- VirtualBox host-only network required host-side adapter repair/creation.

- Dual-NIC setup was required:

-- Host-only provides reliable SSH management from the Windows host.

-- NAT provides stable outbound connectivity for package downloads.

- Cloud-init can override network configuration; it was disabled for persistent netplan control.

- Splunk enforces a minimum free disk threshold for search dispatch; LVM expansion was performed to meet operational requirements.

## Artifacts

- Screenshots: siem/screenshots/

- Config backups: siem/config/

- Troubleshooting notes: siem/runbook/troubleshooting-notes.md

