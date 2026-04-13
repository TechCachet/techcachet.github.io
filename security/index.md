---
layout: default
title: "Security Overview"
permalink: /security/
---

# Security Overview: Tech Cachet

At Tech Cachet, security is a foundational component of our development process. This page provides a detailed overview of our security controls, vulnerability management, and incident response procedures for our Atlassian Forge applications.

---

## 1. Architecture & Data Handling

Our applications are built exclusively on the **Atlassian Forge** platform. This architecture allows us to inherit the robust security and compliance controls provided by Atlassian.

*   **No External Servers:** Tech Cachet does not operate separate application servers or external databases for core app logic. All code execution and data processing occur within the Atlassian Cloud environment.
*   **Data Minimization:** We only request the minimum scopes (Least Privilege) required for functionality. Our apps process Jira issue metadata transiently and do not maintain persistent replicas of your Jira content outside of the Atlassian perimeter.
*   **Storage:** Any application configuration or persistent data is stored in **Forge Key-Value Store (KVS)**, which is encrypted at rest by Atlassian.

---

## 2. Security Controls & SDLC

We follow a secure Software Development Life Cycle (SDLC) to ensure the integrity and security of our code.

*   **Code Reviews:** All changes undergo peer review before deployment to ensure quality and identify potential security flaws.
*   **Automated Scanning:** We utilize Atlassian's **EcoScanner** and GitHub's **Dependabot** to automatically detect vulnerabilities in our code and third-party dependencies.
*   **Modern Runtimes:** Our apps run on the latest supported Node.js runtimes provided by Forge, ensuring we benefit from the latest security patches.
*   **Network Isolation:** Our apps are network-isolated by default. We do not permit unauthorized external data egress, ensuring your Jira data stays within Atlassian.

---

## 3. Vulnerability Management

We are committed to identifying and remediating security vulnerabilities rapidly.

*   **Marketplace Security Bug Bounty Program:** Tech Cachet participates in the Atlassian Marketplace Bug Bounty program via Bugcrowd. We work with independent security researchers to identify and resolve potential issues.
*   **Reporting:** Security vulnerabilities can be reported directly to our security team at [techcachet@gmail.com](mailto:techcachet@gmail.com).
*   **Remediation Timelines:** We adhere to strict remediation SLAs:
    *   **Critical:** 15 days
    *   **High:** 30 days
    *   **Medium/Low:** Best effort based on risk assessment.

---

## 4. Incident Response

In the event of a security incident, Tech Cachet follows a structured response process:

1.  **Identification:** Active monitoring and report ingestion to identify potential breaches or misconfigurations.
2.  **Triage & Containment:** Rapid assessment of the incident scope followed by immediate measures to prevent further impact.
3.  **Resolution:** Deployment of patches or configuration changes to resolve the root cause.
4.  **Notification:** If a security incident affects customer data, we will notify affected customers via their primary Atlassian contact email within **72 hours** of becoming aware of the incident.
5.  **Post-Mortem:** A detailed review of the incident to prevent recurrence and improve our defensive posture.

---

## 5. Security Contact

For questions regarding our security practices or to report a security concern, please contact:

**Security Team**  
Email: [techcachet@gmail.com](mailto:techcachet@gmail.com)  
Subject: "Security Inquiry" or "Security Report"

---

For legal terms and privacy details, please visit our **[Privacy Policy](/privacy/)** and **[Terms of Service](/terms/)**.
