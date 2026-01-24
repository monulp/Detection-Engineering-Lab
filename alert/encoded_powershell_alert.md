# Alert: Encoded PowerShell Execution

## Description
Triggers when PowerShell is executed with encoded commands,
a common obfuscation technique used in malware and post-exploitation.

## Detection Source
Windows Security Event Log  
Event ID: 4688 (Process Creation)

## Trigger Logic
- CommandLine contains -EncodedCommand or -enc
- Alert fires if one or more events occur in 5 minutes

## Severity
High

## Analyst Actions
1. Review CommandLine for malicious indicators
2. Identify parent process
3. Check user context
4. Determine if execution is legitimate or suspicious

## Known False Positives
- Splunk Universal Forwarder internal PowerShell usage
