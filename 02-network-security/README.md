# Network Security Incident Response & Traffic Analysis

## Project Artifacts
* 📄 [View/Download NIST DoS Incident Response Playbook (PDF)](NIST%20Incident%20report%20analysis.pdf)
* 🔍 [View/Download DNS & ICMP Traffic Analyzer Report (PDF)](Cybersecurity%20incident%20report%20network%20traffic%20analysis.pdf)

---

## Executive Summary
This project documents a comprehensive incident response execution and technical log analysis aligned with the **NIST Cybersecurity Framework (CSF)**. Acting as a Cybersecurity Analyst, I investigated and successfully resolved two distinct enterprise network disruptions:
1. A Distributed Denial of Service (DDoS) / SYN Flood attack targeting critical web availability.
2. A localized Domain Name System (DNS) resolution failure diagnosed through raw network packet analysis.

---

## Technical Environment & Tools
* **Framework Alignment:** NIST Cybersecurity Framework (CSF) V1.1/2.0
* **Protocols Analyzed:** TCP/IP, UDP, DNS (Port 53), HTTP/HTTPS, ICMP
* **Defense Strategies:** Network Segmentation, Firewall Rule Optimization, Port Hardening, Ingress Filtering
* **Log Analysis Utilities:** `tcpdump`, Wireshark Packet Inspection

---

## NIST CSF Alignment & Incident Walkthrough

### 🔍 1. Identify
* [cite_start]**Targeted Assets:** Internal corporate web servers and critical customer-facing DNS infrastructure (`www.yummyrecipesforme.com`)[cite: 4, 5].
* [cite_start]**Impact Assessment:** The network experienced an unprecedented spike in raw unauthorized traffic, leading to service degradation, "destination port unreachable" errors, and a total lack of availability for authorized users[cite: 6, 13].

### 🛡️ 2. Protect
* **Firewall Hardening:** Deployed updated access control lists (ACLs) on perimeter firewalls to block verified malicious external source IP addresses and enforce strict ICMP rate limiting.
* **Zone Segmentation:** Isolated compromised public-facing server environments into a secure, segmented subnet to prevent internal lateral movement.
* [cite_start]**Attack Surface Reduction:** Audited system ports, disabled unused services, verified active listening daemons on critical infrastructure ports (like Port 53), and enforced secure administrative connection protocols[cite: 7, 18, 22].

### 👁️ 3. Detect
* **Anomalous Traffic Indicators:** Network monitoring baselines triggered high-severity alerts due to an overwhelming influx of incomplete TCP connection requests and abnormal ICMP packet behaviors.
* [cite_start]**Log Inspection:** Analyzed raw packet capture outputs utilizing `tcpdump` to trace explicit communications between client machine `192.51.100.15` and the target name server `203.0.113.2`, pinpointing structural patterns in the packet flood[cite: 5, 14, 16].

### ⚡ 4. Respond
* **Containment Protocols:** Initiated perimeter rate-limiting, dropped unauthenticated traffic flows, and executed drop-action rules to isolate network segments from active malicious traffic.
* [cite_start]**Mitigation:** Successfully minimized packet load on target resources, allowing internal infrastructure to recover system memory, restore DNS port accessibility, and free up vital processing bandwidth[cite: 18, 22].

### 🔄 5. Recover
* [cite_start]**Service Restoration:** Safely restored standard public-facing network paths after verification of clean traffic lines, verifying that the DNS service daemon was stable and accepting connection requests[cite: 18, 22].
* **Integrity Validation:** Monitored system availability logs and performed automated health checks to guarantee that normal business operations safely and completely resumed without lingering latency.onitored system availability logs and performed automated health checks to guarantee that normal business operations safely resumed.
