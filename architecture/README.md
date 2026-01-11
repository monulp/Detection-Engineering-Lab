# Architecture Overview

This folder contains the high-level architecture for the Detection Engineering Lab.

The architecture represents a small, realistic SOC-style environment designed to
demonstrate how endpoint and server telemetry is collected, centralized, and used
for detection and investigation.

## Components

- **Windows Endpoint**
  - Generates authentication, process execution, and PowerShell telemetry
  - Represents a typical user workstation in an enterprise environment

- **Linux Server**
  - Provides SSH access and authentication logs
  - Represents a common internal or internet-facing service

- **SIEM**
  - Centralized log ingestion and indexing
  - Hosts detection logic and investigation queries

## Design Principles

- Keep the environment intentionally small and explainable
- Focus on telemetry quality over infrastructure scale
- Mirror real-world SOC data flows rather than lab or honeypot setups

This architecture is the foundation for all detection engineering and investigation
work in this project.
