# Detection: Brute Force Followed by Successful Logon (Windows)

## Objective
Detect repeated failed authentication attempts followed by a successful
logon on the same host within a short time window.

## Data Source
Windows Security Event Log (4625, 4624)

## Detection Logic
- Count failed logons (4625) and successful logons (4624)
- Group events in 5-minute windows
- Trigger when failures exceed threshold and at least one success occurs

## SPL
```spl
index=windows_security host=WIN10-ENDPOINT earliest=-30m ("<EventID>4625</EventID>" OR "<EventID>4624</EventID>")
| eval eventid=case(
    match(_raw,"<EventID>4625</EventID>"),4625,
    match(_raw,"<EventID>4624</EventID>"),4624
)
| bin _time span=5m
| stats 
    count(eval(eventid=4625)) as failed_logons
    count(eval(eventid=4624)) as successful_logons
    by host _time
| where failed_logons >= 5 AND successful_logons >= 1
| sort - _time
```

