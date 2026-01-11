# Detection Engineering Lab: Telemetry → Detections → Investigations

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

## Out of Scope (by design)

- Large-scale enterprise simulation

- Honeypots or internet-wide exposure

- Automated SOAR playbooks

- AI-based attack classification

- Red team tooling depth beyond what is needed to generate telemetry
