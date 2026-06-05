# Botium Toys: Internal IT Security Audit & Risk Assessment Report

## 1. Audit Scope & Goals
* **Scope:** The entire security program at Botium Toys[cite: 2]. All assets, internal processes, and procedures related to the implementation of technical, administrative, and physical controls and compliance best practices are within scope[cite: 2].
* **Goals:** Assess existing assets and complete a controls and compliance checklist to identify critical security gaps, determine current regulatory risks/fines, and provide actionable recommendations to improve Botium Toys’ overall security posture[cite: 2].

---

## 2. Inventory of Current Assets
The following corporate assets are actively managed by the IT department[cite: 2]:
* **Hardware & Infrastructure:** On-premises office equipment, end-user devices (desktops, laptops, smartphones), remote workstations, network peripherals, and internal network infrastructure[cite: 2].
* **Physical Security Systems:** Up-to-date closed-circuit television (CCTV) surveillance cameras, building locks, and functioning fire detection/prevention systems[cite: 2].
* **Software & Services:** E-commerce systems, database systems, inventory management platforms, accounting software, and telecommunication systems[cite: 2].
* **Data & Operations:** Internal data storage, data retention systems, internet access points, and legacy end-of-life systems requiring manual monitoring[cite: 2].

---

## 3. Controls Assessment Checklist
This matrix reflects the status of security controls currently implemented or missing at Botium Toys[cite: 1, 2]:

| Control Name | Category | Implemented? | Risk / Purpose[cite: 3] |
| :--- | :--- | :---: | :--- |
| **Least Privilege** | Administrative | ❌ **No**[cite: 1] | High risk; all employees currently have unfettered access to sensitive customer data and cardholder information[cite: 2]. |
| **Disaster Recovery Plans** | Administrative | ❌ **No**[cite: 1] | High threat to business continuity; no documented procedures to recover systems after an incident[cite: 2]. |
| **Password Policies** | Administrative |  **Yes**[cite: 1] | **Inadequate:** Current requirements are nominal and do not meet modern industry complexity rules[cite: 2]. |
| **Separation of Duties** | Administrative | ❌ **No**[cite: 1] | High internal risk; missing checks and balances for sensitive operational tasks[cite: 2]. |
| **Firewall** | Technical |  **Yes**[cite: 1] | Functional; blocks unauthorized traffic based on an appropriately defined set of security rules[cite: 2]. |
| **Intrusion Detection System (IDS)**| Technical | ❌ **No**[cite: 1] | Critical gap; the network cannot detect anomalous malicious traffic or active intrusions in real time[cite: 2]. |
| **Backups** | Technical | ❌ **No**[cite: 1] | High risk of permanent data loss; no secondary copies of critical infrastructure or customer databases exist[cite: 2]. |
| **Antivirus Software** | Technical |  **Yes**[cite: 1] | Functional; installed across endpoints and monitored regularly by the IT team[cite: 2]. |
| **Manual System Monitoring** | Technical |  **Yes**[cite: 1] | Functional but unoptimized; legacy systems are maintained manually but lack a formal, clear schedule[cite: 2]. |
| **Encryption** | Technical | ❌ **No**[cite: 1] | Critical vulnerability; customer credit card data and PII/SPII are stored and transmitted in plaintext[cite: 2]. |
| **Password Management System** | Technical | ❌ **No**[cite: 1] | Operational bottleneck; causes password fatigue and increases internal IT support ticket queues[cite: 2]. |
| **Physical Locks** | Physical |  **Yes**[cite: 1] | Sufficient; physically secures the main office, storefront, and adjoining warehouse[cite: 2]. |
| **CCTV Surveillance** | Physical |  **Yes**[cite: 1] | Sufficient; operational coverage of physical assets and inventory areas[cite: 2]. |
| **Fire Detection & Prevention** | Physical |  **Yes**[cite: 1] | Sufficient; operational alarms and sprinkler infrastructure are fully functioning[cite: 2]. |

---

## 4. Compliance Framework Checklist

### Payment Card Industry Data Security Standard (PCI DSS)
| Best Practice Requirement | Adhered To? | Finding / Gap[cite: 2] |
| :--- | :---: | :--- |
| Only authorized users have access to credit card info[cite: 1]. | ❌ **No**[cite: 1] | All employees have access to internally stored cardholder data[cite: 2]. |
| Card data is stored, accepted, and processed securely[cite: 1]. | ❌ **No**[cite: 1] | Internal infrastructure lacks basic encryption safeguards[cite: 2]. |
| Data encryption procedures are implemented at touchpoints[cite: 1]. | ❌ **No**[cite: 1] | Local databases process transactions entirely in plaintext[cite: 2]. |
| Adopt secure password management policies[cite: 1]. | ❌ **No**[cite: 1] | Lack of a centralized vault or complex criteria compromises account integrity[cite: 2]. |

### General Data Protection Regulation (GDPR)
| Best Practice Requirement | Adhered To? | Finding / Gap[cite: 2] |
| :--- | :---: | :--- |
| E.U. customers' data is kept private and secured[cite: 1]. | ❌ **No**[cite: 1] | Clear data privacy vulnerability due to total absence of database encryption[cite: 2]. |
| 72-hour data breach notification plan is active[cite: 1]. |  **Yes**[cite: 1] | Successfully established a formal incident notification workflow for E.U. clients[cite: 2]. |
| Data is properly classified and inventoried[cite: 1]. | ❌ **No**[cite: 1] | The IT team cannot determine exactly which specific assets are currently exposed[cite: 2]. |
| Enforce data privacy policies and documentation[cite: 1]. |  **Yes**[cite: 1] | Corporate privacy rules are fully developed and mandated across current staff[cite: 2]. |

### System and Organization Controls (SOC Types 1 & 2)
| Best Practice Requirement | Adhered To? | Finding / Gap[cite: 2] |
| :--- | :---: | :--- |
| User access policies are established[cite: 1]. | ❌ **No**[cite: 1] | Access control models for operational constraints are entirely unmapped[cite: 2]. |
| Sensitive data (PII/SPII) remains strictly confidential[cite: 1]. | ❌ **No**[cite: 1] | Open internal permissions allow anyone to view sensitive corporate files[cite: 2]. |
| Data integrity ensures validated, complete information[cite: 1]. |  **Yes**[cite: 1] | Confirmed; IT controls ensure internal communication logs remain accurate[cite: 2]. |
| Data remains highly available to authorized parties[cite: 1]. |  **Yes**[cite: 1] | Confirmed; infrastructure allows rapid, uninterrupted access for staff[cite: 2]. |

---

## 5. Strategic Security Recommendations
Based on an overall risk score of **8 out of 10**[cite: 2], Botium Toys must immediately implement these high-priority mitigations to achieve proper compliance alignment and safeguard assets:

1. **Enforce the Principle of Least Privilege (PoLP):** Implement a role-based access control (RBAC) model[cite: 3]. Restrict customer PII/SPII and cardholder data access exclusively to essential financial and administrative personnel[cite: 2, 3].
2. **Deploy Cryptographic Protection:** Implement strong encryption mechanisms (AES-256) for all credit card transaction touchpoints, local database tables, and transit channels to achieve compliance with PCI-DSS and GDPR regulations[cite: 1, 2].
3. **Establish an Incident Detection Architecture:** Install an Intrusion Detection System (IDS) to actively monitor internal network segments for malicious traffic patterns or unauthorized network scanning[cite: 2, 3].
4. **Build Operational Resilience:** Formulate and test a localized Disaster Recovery Plan accompanied by automated, off-site daily backups of critical infrastructure configurations and enterprise data sets[cite: 2, 3].
5. **Modernize Credential Security:** Deploy a centralized Enterprise Password Management tool to systematically enforce strict password length, complexity, and rotational timelines across all corporate systems[cite: 2, 3].
