# Detection: Encoded PowerShell Execution

## Objective
Detect PowerShell executions using encoded commands (e.g., -EncodedCommand / -enc),
a common technique for obfuscation and payload delivery.

## Data Source
Windows Security Event Log (Process Creation, Event ID 4688)

## Detection Logic
Search for process creation events where the command line contains
-EncodedCommand or -enc and the process is powershell.exe or pwsh.exe.

## SPL
```spl
index=windows_security host=WIN10-ENDPOINT "<EventID>4688</EventID>" ("powershell.exe" OR "pwsh.exe") ("-enc" OR "-encodedcommand" OR "EncodedCommand")
```
