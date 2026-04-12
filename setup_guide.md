# Setup Guide – Atomic Red Team Threat Hunting Lab

## Overview

This guide explains how to set up a lab environment to simulate adversary techniques using Atomic Red Team and analyze logs using Wazuh SIEM.

---

## Requirements

### Systems

* Wazuh Server (Ubuntu 20.04+)
* Windows 10 Endpoint

---

## Network Configuration

Ensure both systems are in the same network.

In this lab:

* Wazuh Server: 192.168.56.102
* Windows Endpoint: 192.168.56.105

---

## Step 1 – Install Wazuh Agent

1. Install Wazuh agent on Windows
2. Connect it to the Wazuh manager

Verify:

* Agent appears in dashboard

---

## Step 2 – Enable Logging

Run as Administrator:

```powershell
auditpol /set /subcategory:"Logon" /success:enable /failure:enable
```

---

## Step 3 – Enable PowerShell Execution

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force
```

---

## Step 4 – Install Atomic Red Team

```powershell
IEX (IWR 'https://raw.githubusercontent.com/redcanaryco/invoke-atomicredteam/master/install-atomicredteam.ps1' -UseBasicParsing)
cd C:\AtomicRedTeam\invoke-atomicredteam\
Install-Module -Name powershell-yaml
Import-Module .\Invoke-AtomicRedTeam.psm1
```

---

## Step 5 – Execute Techniques

### T1003 – Credential Dumping

```powershell
Invoke-AtomicTest T1003
```

---

### T1057 – Process Discovery

```powershell
Invoke-AtomicTest T1057
```

---

### T1082 – System Information Discovery

```powershell
Invoke-AtomicTest T1082
```

---

### T1110 – Brute Force

```powershell
Invoke-AtomicTest T1110.001
```

---

## Step 6 – Monitor Logs

On Wazuh server:

```bash
sudo tail -f /var/ossec/logs/alerts/alerts.json
```

---

## Step 7 – Threat Hunting Queries

### Process creation

data.win.system.eventID:4688 OR 600

### Authentication events

data.win.system.eventID:4624 OR 4625

### Suspicious processes

powershell OR cmd.exe OR tasklist OR security

---

## Step 8 – Analysis

* Identify unusual activity
* Correlate events
* Detect suspicious patterns

---

## Troubleshooting

### Atomic tests fail

* Run:
  Invoke-AtomicTest <technique>

### No logs appear

* Verify agent is connected
* Check logging configuration

---

## Security Notes

* Use only in isolated lab environment
* Do not expose to internet

---

## Validation Checklist

* [ ] Agent connected
* [ ] Atomic installed
* [ ] Techniques executed
* [ ] Logs detected in Wazuh
* [ ] Analysis completed
