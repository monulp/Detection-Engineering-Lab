# Detection Engineering Lab: Telemetry → Detections → Investigations    Status: (ongoing)

## 1. Objective

The objective of this project is to design and implement a realistic, small-scale detection engineering lab that mirrors how a modern Security Operations Center (SOC) detects, investigates, and tunes security alerts.

## This project focuses on:

- Collecting high-quality endpoint and server telemetry

- Simulating real-world attack techniques in a controlled environment

- Writing and iteratively tuning detections to reduce false positives

- Investigating alerts using structured SOC-style workflows

- Documenting detection logic, investigation steps, and tuning decisions

## 2. Scope and Boundaries (important for interviews)

## In Scope

- One Windows endpoint (user workstation)

- One Linux server (SSH-enabled)

- Centralized log collection using a SIEM

- Detection logic based on host and authentication telemetry

- Manual, explainable detection logic (no black-box automation)

- SOC-style alert triage and investigation documentation

## Out of Scope

- Large-scale enterprise simulation

- Honeypots or internet-wide exposure

- Automated SOAR playbooks

- AI-based attack classification

- Red team tooling depth beyond what is needed to generate telemetry

## 3. Requirements

## 3.1 Technical Requirements

### Infrastructure

- Virtualization platform (VirtualBox or VMware)

- Ability to run at least 3 virtual machines concurrently

### Virtual Machines

- Windows 10/11 endpoint

- Ubuntu Server (SSH enabled)

- SIEM server (Splunk or Elastic)

### Networking

- Internal network (NAT or Host-only)

- All systems must communicate with the SIEM

### Logging & Telemetry

- Windows Security Event Logs

- Windows Sysmon logs

- Linux authentication and system logs

- Centralized ingestion into SIEM

### SIEM Capabilities

- Log search and filtering

- Field extraction and normalization

- Alerting/detection logic

- Timestamped event correlation

## 3.2 Knowledge & Skills Requirements

This project assumes:

- Basic Windows and Linux administration

- Understanding of authentication concepts (logon, SSH, sudo)

- Familiarity with SIEM concepts (indexes, sourcetypes, queries)

- MITRE ATT&CK at a conceptual level (techniques, not memorization)

- Willingness to read logs carefully (this is non-negotiable)

## 4. Summary

This project implements a mini detection engineering program that reflects how security teams operate in real production environments. Rather than focusing on tool sprawl or automation, the project emphasizes signal quality, alert logic, and investigative reasoning.

By progressing from raw telemetry to refined detections and documented investigations, the project demonstrates hands-on capability in:

- Security monitoring

- Detection development

- False positive reduction

- Incident analysis

- Security documentation
