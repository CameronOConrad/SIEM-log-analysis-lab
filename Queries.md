# Splunk Detection Queries

## Failed Windows Login Attempts
Detects multiple failed login attempts on a Windows system.

```spl
index=main EventCode=4625
| stats count by Account_Name, host
| where count >= 5
```

 ## Failed Linux SSH Authentication Attempts

Detects repeated failed SSH login attempts.  

```
index=main sourcetype=linux_secure "Failed password"
| stats count by user, host
| where count >= 3
````
## Event Spike Detection (Reconnaissance Indicator)

Detects abnormal spikes in log volume, which may indicate scanning or enumeration activity.

```
index=main
| bin _time span=1m
| stats count by _time, host
| where count > 100
```

## SSH-Based Scan Indicator (Linux)

Detects a high number of SSH-related events from a single source.

```
index=main sourcetype=linux_secure
| stats count by src_ip, host
| where count > 10
```
