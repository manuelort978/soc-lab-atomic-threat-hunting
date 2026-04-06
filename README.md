# Atomic Red Team & Wazuh – Threat Hunting Lab

## Overview

This project simulates adversary techniques using Atomic Red Team and analyzes system behavior using Wazuh SIEM.

The lab focuses on threat hunting instead of predefined detection rules, replicating real-world SOC workflows.

---

## Objectives

* Simulate MITRE ATT&CK techniques
* Analyze Windows logs in Wazuh
* Identify suspicious behavior
* Develop threat hunting skills

---

## Techniques Executed

 Technique | Description                    
 --------- | ------------------------------ 
 T1003     | Credential Dumping (simulated) 
 T1057     | Process Discovery              
 T1082     | System Information Discovery   
 T1110     | Brute Force (simulated)        

---

## Methodology

This lab follows a threat hunting approach:

1. Execute attack simulation
2. Collect logs in Wazuh
3. Query and analyze events
4. Identify suspicious patterns

---

## Key Findings

* Suspicious process execution detected
* System reconnaissance activity observed
* Potential brute-force patterns identified
* Evidence of credential access simulation

---

## Skills Demonstrated

* Threat Hunting
* SIEM Analysis (Wazuh)
* MITRE ATT&CK Mapping
* Log Analysis
* Incident Investigation

---

## Project Structure

* `/techniques` → Documentation per technique
* `/reports` → Final analysis
* `/queries` → Hunting queries used

---

## Future Improvements

* Create detection rules in Wazuh
* Automate alerts
* Integrate threat intelligence feeds
