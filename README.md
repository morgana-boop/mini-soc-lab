# 🛡️ Mini SOC Lab — Detection Engineering & Threat Simulation

A hands-on Security Operations Center (SOC) home lab designed to simulate real-world attack scenarios, centralize telemetry, develop detection logic and perform incident investigation.

This project demonstrates practical skills across **Blue Team monitoring, Red Team attack simulation and defensive security engineering** using a controlled virtualized environment.

---

## Objective

Build and operate a small-scale SOC environment capable of:

- Centralizing logs from Windows and Linux endpoints  
- Simulating adversarial activity (brute force, PowerShell abuse, privilege escalation)  
- Developing custom SIEM detection rules  
- Investigating alerts and constructing incident timelines  
- Mapping attacker behavior to threat frameworks  
- Producing structured incident reports  

---

## Skills Demonstrated

- Security Monitoring & Log Analysis  
- Detection Engineering  
- Threat Hunting Fundamentals  
- Incident Response Methodology  
- Attack Simulation (Red Team mindset)  
- SIEM Deployment & Administration  
- Network & Endpoint Telemetry Analysis  

---

## Lab Architecture

The environment consists of:

- SIEM Server (log aggregation, correlation, alerting)  
- Windows target machine  
- Linux target machine  
- Attacker machine used to generate controlled attack traffic  

Logs are forwarded from endpoints to the SIEM where detection rules are applied and alerts are investigated through the dashboard interface.

---

## Simulated Attack Scenarios

- SSH brute force authentication attempts  
- Suspicious PowerShell command execution  
- Privilege escalation events  
- User creation and administrative group abuse  

Each scenario includes:

- Attack command execution  
- Expected log artifacts  
- Detection logic  
- Investigation notes  
- Evidence screenshots  

---

## Investigation & Analysis

For every triggered alert the project documents:

- Attack timeline reconstruction  
- Source IP attribution  
- Target account analysis  
- Detection effectiveness evaluation  

---

## Threat Framework Mapping

Observed attacker techniques are mapped to industry-standard adversary behavior frameworks to contextualize detection coverage and defensive maturity.

---

## Repository Structure


mini-soc-lab/
├── architecture
├── detections
├── investigation
├── incident-report
├── attack-scenarios
├── evidence
├── diagrams
└── queries


---

## Purpose of This Project

This lab serves as a practical cybersecurity artifact demonstrating the ability to:

- Design security monitoring environments  
- Think from both attacker and defender perspectives  
- Transform raw logs into actionable intelligence  
- Communicate incidents using structured technical reporting  

It represents foundational experience aligned with entry-level SOC Analyst, Detection Engineer and Junior Pentester roles.

---
