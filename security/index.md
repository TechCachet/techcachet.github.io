---
layout: default
title: "Security Overview"
---

# Security Overview

**Linked SLA Alerts** (Atlassian Forge app for Jira Cloud) · **Tech Cachet**

This page is a concise summary for **enterprise admins** and **security reviewers**. It is **not** a certification, penetration test, or legal document. For full privacy and data practices, see the **[Privacy Policy](/privacy/)**.

---

## Architecture

The app runs **entirely on Atlassian Forge**. Tech Cachet does **not** operate separate **application servers** or **external databases** for core app logic. Processing and **Forge app storage (Key-Value Store)** use **Atlassian’s** infrastructure.

---

## Data handling

The app accesses **Jira** data (issues, links, SLA-related fields, users, and configuration) **only within the permissions** of the installed app and the **user’s** Jira access. We do **not** maintain a separate Tech Cachet copy of your Jira database for routine operation. **Customer Jira content** remains under **your** and **Atlassian’s** control.

---

## Encryption and transport

Data **at rest** in Forge app storage is **encrypted** as described in **Atlassian** documentation for Forge/KVS. Traffic between the app and Jira, Slack, and allowlisted webhook endpoints uses **HTTPS (TLS)**.

---

## Secrets management

**Slack bot tokens** and similar secrets you provide are stored in **Forge Key-Value Store**. Tokens are **masked** in API responses where the product implements masking, and admins can **clear** stored tokens in the admin UI when supported.

---

## Outbound requests (`external.fetch`)

Outbound calls from the app are limited to **hostnames allowed** in the published **`manifest.yml`** **`external.fetch`** allowlist (for example **Atlassian** product domains, **Slack**, and permitted automation/webhook hosts). **Arbitrary URLs** are **not** allowed.

---

## Vulnerability disclosure

To report a security issue in the **Linked SLA Alerts** app, email **techcachet@gmail.com** (subject **“Security report: Linked SLA Alerts”**) with a description, reproduction steps, and impact. Reports are handled **privately** through this mailbox, **not** via a public tracker and **not** by posting to **GitHub**; you are **not** required to publish vulnerabilities.

**Full policy** (supported versions, timelines, scope, coordinated disclosure): **[Vulnerability disclosure policy](/vulnerability-disclosure/)**.

---

## Incident response

If Tech Cachet identifies a **security incident** that **affects customer data** in a way that requires customer notification, we will notify **affected customers by email** within **72 hours** of becoming **aware** of the incident (subject to **lawful** instructions and the need to **preserve** an investigation).

Notifications will aim to include: **what happened**, **what categories of data** were involved, **steps we are taking**, and **how to contact** Tech Cachet with questions.

**Contact:** [techcachet@gmail.com](mailto:techcachet@gmail.com)

---

## Contact (general security questions)

**techcachet@gmail.com**: use subject line **“Security report: Linked SLA Alerts”** for vulnerabilities; **private email only** (see **[Vulnerability disclosure policy](/vulnerability-disclosure/)**).

For product support and policy links, see **[Support & Security](/support/)** and **[Legal & Trust](/legal/)**.



