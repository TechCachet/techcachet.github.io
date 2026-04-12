---
layout: default
title: "Security Overview"
---

# Security Overview

**Tech Cachet** (Atlassian Forge apps for Jira Cloud)

This page is a concise summary for **enterprise admins** and **security reviewers**. For full privacy and data practices, see the **[Privacy Policy](/privacy/)**.

---

## Architecture

Our apps run **entirely on Atlassian Forge**. Tech Cachet does **not** operate separate **application servers** or **external databases** for core app logic. Processing and **Forge app storage (Key-Value Store)** use **Atlassian’s** infrastructure.

---

## Data handling

Our apps access **Jira issue metadata** (e.g., status, dates, priorities) **only within the permissions** of the installed app and the **user’s** Jira access. We do **not** maintain a separate Tech Cachet copy of your Jira database. **Customer Jira content** remains under **your** and **Atlassian’s** control.

---

## Encryption and transport

Data **at rest** in Forge app storage is **encrypted** as described in **Atlassian** documentation for Forge/KVS. Traffic between our apps and Jira uses **HTTPS (TLS)**.

---

## Secrets management

Any configuration secrets provided to our apps are stored in the **Forge Key-Value Store**. We minimize the storage of sensitive data and follow Atlassian's best practices for secure storage.

---

## Outbound requests

Our current production apps are **network-isolated** and do not make outbound requests to third-party services. All processing and visualization occur within the Atlassian Cloud environment.

---

## Vulnerability disclosure

To report a security issue in any **Tech Cachet** app, email **techcachet@gmail.com** (subject **“Security report”**) with a description, reproduction steps, and impact. Reports are handled **privately** through this mailbox.

**Full policy:** **[Vulnerability disclosure policy](/vulnerability-disclosure/)**.

---

## Incident response

If Tech Cachet identifies a **security incident** that **affects customer data**, we will notify **affected customers by email** within **72 hours** of becoming **aware** of the incident (subject to lawful instructions).

**Contact:** [techcachet@gmail.com](mailto:techcachet@gmail.com)

---

## Contact

**techcachet@gmail.com**: use subject line **“Security report”** for vulnerabilities.

For product support and policy links, see **[Support & Security](/support/)** and **[Legal & Trust](/legal/)**.
