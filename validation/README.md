## Telemetry Validation

Telemetry was validated before detection development.

Validation steps included:
- Confirming audit coverage with `auditpol`
- Verifying event presence locally in Event Viewer
- Confirming ingestion in Splunk
- Measuring ingestion delay using `_time` vs `_indextime`

Only after validation were detections developed.
