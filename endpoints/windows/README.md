# Windows Endpoint (WIN10-ENDPOINT)

## Purpose
This Windows 10 Pro virtual machine represents a corporate workstation.
It is used to generate realistic endpoint telemetry for detection engineering.

The system intentionally performs both benign and malicious-like actions
to validate SIEM visibility and detection logic.

---

## Platform
- OS: Windows 10 Pro (64-bit)
- Role: Endpoint / Workstation
- Hypervisor: VirtualBox

---

## VM Specifications
- CPU: 2 vCPU
- Memory: 4 GB
- Disk: 60 GB (dynamic)
- Network: Host-only (SIEM reachable)

---

## Naming
- Hostname: WIN10-ENDPOINT
- Primary user: analyst

---

## Telemetry Goals
This endpoint is used to generate:
- Authentication events
- Process creation events
- PowerShell execution events

Telemetry is forwarded to Splunk using the Splunk Universal Forwarder.

## Build Status
- Windows 10 Pro installed
- Host-only networking confirmed
- Baseline snapshot created

