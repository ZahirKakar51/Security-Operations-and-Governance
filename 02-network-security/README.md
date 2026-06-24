# Network Security Incident Response & Traffic Analysis

## Executive Summary
This project documents a comprehensive incident response execution aligned with the **NIST Cybersecurity Framework (CSF)**. Acting as a Cybersecurity Analyst, I investigated and successfully mitigated a network disruption caused by a Distributed Denial of Service (DDoS) / SYN Flood attack targeting an organization's critical internal web services. 

---

## Technical Environment & Tools
* **Framework Alignment:** NIST Cybersecurity Framework (CSF) V1.1/2.0
* **Protocols Analyzed:** TCP/IP, DNS, HTTP, ICMP
* **Defense Strategies:** Network Segmentation, Firewall Rule Optimization, Port Hardening
* **Log Analysis Utilities:** `tcpdump`, Wireshark Packet Inspection

---

## NIST CSF Alignment & Incident Walkthrough

### 🔍 1. Identify
* **Targeted Assets:** Internal corporate web servers and critical customer-facing DNS infrastructure.
* **Impact Assessment:** The network experienced an unprecedented spike in raw outbound/inbound traffic, leading to service degradation and total lack of availability for authorized users.

### 🛡️ 2. Protect
* **Firewall Hardening:** Deployed updated access control lists (ACLs) on perimeter firewalls to block verified malicious external source IP addresses.
* **Zone Segmentation:** Isolated compromised public-facing server environments into a secure, segmented subnet to prevent internal lateral movement.
* **Attack Surface Reduction:** Audited system ports, disabled unused services, and enforced secure administrative connection protocols.

### 👁️ 3. Detect
* **Anomalous Traffic Indicators:** Network monitoring baselines triggered high-severity alerts due to an overwhelming influx of incomplete TCP connection requests.
* **Log Inspection:** Analyzed raw packet capture outputs utilizing network utilities to pinpoint structural patterns in the packet flood.

### ⚡ 4. Respond
* **Containment Protocols:** Initiated perimeter rate-limiting and drop-action rules to isolate network segments from active malicious traffic flows.
* **Mitigation:** Successfully minimized packet load on target resources, allowing internal infrastructure to recover system memory and processing bandwidth.

### 🔄 5. Recover
* **Service Restoration:** Safely restored standard public-facing network paths after verification of clean traffic lines.
* **Integrity Validation:** Monitored system availability logs and performed automated health checks to guarantee that normal business operations safely resumed.
