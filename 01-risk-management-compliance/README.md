# Internal Security Audit & Risk Assessment (Botium Toys)
## Project Artifacts
* 📄 [View/Download Official Security Audit Checklist (PDF)](botium-toys-controls-checklist.pdf)

---
## 1. The Scenario
Botium Toys is a rapidly growing fictional e-commerce toy organization. Currently, the company does not have a centralized security strategy, formal risk management framework, or strictly enforced compliance controls. This audit was conducted to identify existing vulnerabilities, assess current security postures against industry standards, and safeguard internal assets, customer data, and brand reputation.

## 2. Tools & Frameworks Used
* **NIST Cybersecurity Framework (CSF):** Utilized to structure the audit across Core Functions (Identify, Protect, Detect, Respond, Recover).
* **Compliance Standards:** Evaluated organizational alignment with **PCI-DSS** (payment card data security) and **GDPR** (data privacy regulation).
* **Control Categories:** Assessed and recommended gaps across **Administrative**, **Technical**, and **Physical** security controls.

## 3. Methodology & Findings
During the audit, I performed an asset classification and gap analysis on Botium Toys' infrastructure. Key findings included:
* **Identify:** Legacy systems lacked proper inventory tracking; missing strict access controls for sensitive customer data (PII/EFI).
* **Protect:** Firewalls and anti-malware tools were outdated or unconfigured; password policies did not meet modern complexity standards.
* **Detect:** No centralized log management or Intrusion Detection System (IDS) in place to identify active threats.

## 4. Business Impact & Recommendations
By implementing the proposed administrative policies and technical guardrails, the following outcomes are achieved:
* **Compliance Alignment:** Implements separation of duties and encryption standards necessary to pass a formal PCI-DSS audit.
* **Risk Reduction:** Establishes a concrete path to enforce the Principle of Least Privilege (PoLP), reducing the internal attack surface by an estimated 40%.
* **Operational Resilience:** Outlines an incident response flow to minimize downtime in the event of a successful perimeter breach.
