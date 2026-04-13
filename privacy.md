---
layout: default
title: Privacy Policy
permalink: /privacy/
---

# Privacy Policy

**Last updated:** April 2026

**Publisher:** Tech Cachet, LLC.

This Privacy Policy describes how Tech Cachet apps access, use, store, and share information when a customer installs and uses our apps in their Jira Cloud site.

---

## 1. Summary

- **Architecture:** Tech Cachet apps run **entirely on Atlassian Forge**. Core processing and **Forge app storage** are on **Atlassian’s infrastructure**. Tech Cachet does **not** operate separate **application servers** or **external databases** for core app logic.
- **Data Access:** Our apps read Jira **issue metadata** (e.g., status, dates, priorities) to power dashboards and security scans. This data is processed **transiently** to generate insights and is not persisted by Tech Cachet outside of the Atlassian perimeter.
- **No External Egress:** Our current apps do **not** send data to third-party services (such as Slack or external webhooks). All analysis and visualization happen within your Jira instance.
- **Personal Data:** We minimize the use of personal data. We do **not** collect or store Jira user account IDs or email addresses in any external Tech Cachet database.
- **Billing:** Handled exclusively by **Atlassian**. Tech Cachet never sees or stores your payment card information.

---

## 2. Who we are

**Tech Cachet, LLC** builds practical tools for Atlassian teams.

**Contact & Support:** [privacy@techcachet.com](mailto:privacy@techcachet.com) · [Support & Security](https://techcachet.com/support/)

---

## 3. Data Processing

For processing **inside your Jira Cloud tenant**, Tech Cachet acts as a **processor**. Data handling is governed by your agreement with **Atlassian**. Tech Cachet does not maintain off-site replicas of your Jira content.

---

## 4. Categories of personal data (examples)

| Category | Source | Use |
|----------|--------|-----|
| **Jira issue metadata** | Jira REST APIs | Dashboard insights and risk analysis |
| **Jira user identifiers** | Jira API | Transient display of assignees in the app UI |
| **App configuration** | Admin UI | Stored in **Forge secure storage** |

---

## 5. Purposes of processing

- To provide **real-time dashboard insights** into queue health and workflow risks.
- To detect **sensitive data** (e.g., Secrets Finder) within the Atlassian perimeter.
- To maintain **app settings** and user preferences.

---

## 6. Sub-processors

Tech Cachet relies on **Atlassian** (Jira Cloud, Forge runtime, Forge KVS) to process data on your behalf. We do **not** share your Jira data with any other third-party analytics or marketing providers. See our **[Subprocessors & Infrastructure](https://techcachet.com/subprocessors/)**.

---

## 7. Data storage and retention

- **Operational Data:** Issue bodies and metadata remain in **Jira**.
- **Forge KVS:** Stores your specific app configurations (e.g., JQL filters and thresholds).
- **Support email:** Correspondence is retained for up to 2 years for routine business records.

---

## 8. Marketing site (techcachet.com)

This site is a static site hosted on **GitHub Pages**. We do **not** use tracking cookies or third-party analytics on this site.

---

## 9. Changes

We will update the **Last updated** date when we make material changes to how our apps handle data.
