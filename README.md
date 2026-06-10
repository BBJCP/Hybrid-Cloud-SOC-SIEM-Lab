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

### 3. Central Web Console Verification
Successfully authenticated to the visual security operations panel over the secure internal network. The console successfully registered the baseline analytical metrics.
<img width="1041" height="860" alt="dual_fleet_active" src="https://github.com/user-attachments/assets/8c4a0bb0-894e-429a-8ca4-e56d6cf0397c" />


---

## 🛑 Phase II: Red Team Attack Simulations & Incident Profiling

### 1. Windows Enterprise Client Authentication Intrusion Vector
* **Attack Vector Simulation**: Initiated an intentional, high-volume endpoint authentication brute-force stress sequence using native administrative spoofing mechanisms mapping directly to **MITRE ATT&CK T1110 (Brute Force)**. 
* **Telemetry Findings & SIEM Analysis**: The host-based XDR agent sensor immediately intercepted the consecutive login violations. The data stream cleanly extracted and parsed native Windows Security Event ID **4625 (An account failed to log on)**. The metric dashboard records logged a massive alert volume spike exceeding 600+ hits, extracting granular tracking parameters directly into the analytical table interface for threat isolation and containment profiling.

![Centralized SIEM Brute Force Detection Alert]
<img width="1125" height="824" alt="brute_force_detected" src="https://github.com/user-attachments/assets/70a0d117-123b-4db2-9b6b-e0775b7a2386" />

---

## 🛡️ Phase III: Hardening & Enterprise Remediation Strategies

To mitigate the active brute-force threat vector analyzed during the Red Team simulation phase, the following enterprise-grade defensive hardening configurations were engineered to minimize the hybrid infrastructure's attack surface:

### 1. Implementing Account Lockout Threshold Policies (Windows Node)
* **Defensive Strategy**: Configured a local group security policy restriction to automatically lock out any user identity account after 5 consecutive unauthenticated validation attempts. This neutralizes automated dictionary scanning scripts entirely.
* **Implementation Mechanism**: Leveraged administrative controls to enforce threshold limits via the Local Security Policy domain manager:
  `Account Policies -> Account Lockout Policy -> Account lockout threshold = 5`

### 2. Disabling Plain-Text Password Authentication (Linux Server Node)
* **Defensive Strategy**: Modified the core secure-shell daemon configuration on the Ubuntu production instance to enforce cryptographic key-pair routing, completely removing password guessing vectors across internal ports.
* **Implementation Mechanism**: Hardened parameters inside `/etc/ssh/sshd_config` by explicitly defining:
  `PasswordAuthentication no`
  `PubkeyAuthentication yes`

### 3. Management Interface Network Isolation (Network Infrastructure)
* **Defensive Strategy**: Transitioned critical administrative communication boundaries (such as RDP port 3389 and SSH port 22) off public-facing listening scopes, wrapping them natively behind an authenticated Virtual Private Network (VPN) layer to deny external line-of-sight network discovery.
