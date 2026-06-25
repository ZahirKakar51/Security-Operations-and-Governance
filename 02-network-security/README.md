# Network Security Incident Response & Traffic Analysis

## Project Artifacts
* 📄 [View/Download NIST Incident Report Analysis (PDF)](NIST%20Incident%20report%20analysis.pdf)
* 🔍 [View/Download Cybersecurity Incident Report: Network Traffic Analysis (PDF)](Cybersecurity%20incident%20report%20network%20traffic%20analysis.pdf)

---

## 1. NIST Incident Report Analysis (ICMP Flood DoS Attack)

### Summary
A company experienced a DoS attack through an unconfigured firewall which allowed the attacker to send a flood of ICMP packets which overwhelm the company’s networks. The team responded by blocking ICMP packets, stopping all non-critical network services offline, and restoring critical network services.

### NIST Framework Alignment
* **Identify:** A DoS attack through an unconfigured firewall which overwhelmed the company internal networks with ICMP packets.
* **Protect:** The cybersecurity team implemented a new firewall rule to limit the rate of ICMP packets, source IP address verification for spoofed IP addresses, and IDS/IPS to monitor, filter and block traffic based on suspicious characteristics.
* **Detect:** The cybersecurity team configured Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets.
* **Respond:** The incident management team responded to the attack by blocking ICMP packets, isolating affected systems and restoring essential network services. After containment, the team performed a root cause analysis and updated the incident response plan to protect the company from such incidents in the future.
* **Recover:** The network was fully restored after two hours of downtime. A post-incident review was conducted to strengthen policies, implement regular firewall audits, and test the resilience of backup systems. The organization also documented lessons learned and trained staff on future DDoS response procedures.

---

## 2. Network Traffic Analysis (DNS Resolution Failure)

### Scenario & Symptoms
Several customers reported that they were not able to access the website `www.yummyrecipesforme.com` and saw the error message "destination port unreachable" after waiting for the page to load at timestamp `13:24.192571`.

### Technical Investigation & Findings
The IT department loaded the `tcpdump` network analyzer tool to investigate the incident and found the following:
* **Outbound Traffic:** The client browser (`192.51.100.15`) sent a UDP DNS query to the DNS server (`203.0.113.2`) on port 53 requesting an A record to change the domain name into an IP address.
* **Inbound Response:** The analyzer showed that instead of a standard reply, the client received ICMP packets containing the error message: `udp port 53 unreachable`.
* **Consistency:** This error occurred consistently across three separate ICMP responses, confirming the issue was not transient. The browser was unable to resolve the domain name to an IP address, which prevented the HTTPS request from being sent to the web server.

### Suspected Root Cause
The DNS server responded with `udp port 53 unreachable`, which indicates that no DNS service was listening on port 53 of the server, causing the query to fail. A likely cause is that the DNS service on the server was stopped, crashed, or was intentionally disabled, or a firewall/security group is blocking UDP traffic on port 53.
