# Hybrid-Cloud-SOC-SIEM-Lab
An enterprise-grade defensive security engineering home lab using Wazuh SIEM/XDR to monitor hybrid endpoint telemetry and map threat vectors.
# Hybrid Enterprise Threat Detection & Incident Response SIEM Lab

## 📌 Project Objective
This project demonstrates the deployment of a hybrid enterprise log collection and security monitoring architecture using Wazuh SIEM/XDR. The objective was to engineer a central security monitoring server, onboard telemetry streams from both Windows 11 client nodes and Ubuntu Linux servers, simulate threat actor intrusion vectors, and analyze centralized log data to map alerts against real-world attack frameworks.

## 🛠️ Core Skills & Technologies Demonstrated
* **Enterprise SIEM/XDR Implementation**: Wazuh Multi-Component Architecture Deployment
* **Hybrid Systems Logging**: Windows Security Event Forwarding & Linux Syslog Integration
* **Threat Simulation & Analysis**: Command & Control (C2) signatures and brute-force detection
* **Framework Mapping**: Aligning technical telemetry to the MITRE ATT&CK Framework

## 🌐 Lab Infrastructure & Network Topology
* **SIEM Management Engine**: Ubuntu Server Linux Node running Wazuh Multi-Component Stack (IP: `10.0.2.3`)
* **Endpoint Workstation Client**: Windows 11 Enterprise (IP: `10.0.2.16`)
* **Enterprise Linux Node**: Ubuntu Desktop Server Client (IP: `10.0.2.17`)

---

## 🏗️ Phase I: Infrastructure Onboarding & Build Logs

### 1. Central SIEM Node Automated Deployment
The server infrastructure was built utilizing an automated shell deployment manager. Hardware constraint checks were dynamically bypassed utilizing system flag variables (`-i`) to allow baseline functionality on testing virtual environments.

1. Central SIEM Node Automated Deployment
<img width="1919" height="1036" alt="wazuh_install_complete" src="https://github.com/user-attachments/assets/8c3972e6-0805-4f3b-9fcf-ad2d617186ae" />


### 2. Connected Endpoint Fleet Telemetry
The endpoint deployment phase was executed by configuring a lightweight background telemetry daemon on the target Ubuntu Linux node and mapping its transmission destination properties to the central SIEM.
<img width="1290" height="894" alt="ubuntu_agent_active" src="https://github.com/user-attachments/assets/5967c466-1e84-4e1e-9cfa-fd8364b6b36c" />


---

## 🛑 Phase II: Red Team Attack Simulations & Incident Profiling
[This section will document the automated brute force logs we generate next]

---

## 🛡️ Phase III: Hardening & Enterprise Remediation Strategies
[This section will document how we block these specific attacks]
