# SIEM Setup

## Overview
This section documents the setup of the SIEM platform used in this lab.
Splunk Enterprise was selected to mirror common SOC environments and to
support SPL-based detection engineering and alert development.

## SIEM Platform
- Product: Splunk Enterprise
- OS: Ubuntu Server 24.04 LTS
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
