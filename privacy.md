---
layout: default
title: Privacy Policy
permalink: /privacy/
---

# Privacy Policy

**Last updated:** April 2026

**Publisher:** Tech Cachet, LLC.

This Privacy Policy describes how Tech Cachet apps access, use, store, and share information when a customer installs and uses our apps in their Jira Cloud site. It also describes our marketing site.

---

## 1. Summary

- Tech Cachet apps run **entirely on Atlassian Forge**. Core processing and **Forge app storage** are on **Atlassian’s infrastructure**. Tech Cachet does **not** operate separate **application servers** or **external databases** for core app logic. If we add **optional external backends** (e.g. Forge Remote or other services) later, we will **update this policy** and relevant Marketplace materials.
- Our apps read Jira **issue** data to power dashboards, intake workflows, and security scans. Processing is typically event-driven (e.g., when a user interacts with a gadget or issue panel), not a **scheduled** background job watching issues in the background.
- **Personal data** is processed where needed for features, including **Jira account identifiers**, **display names**, and **work content** in issues.
- **Billing** is handled by **Atlassian**. Payment card data is handled by **Atlassian**, **not** collected or stored by Tech Cachet.
- **Location / transfers:** Processing on **Forge** uses **Atlassian’s** global infrastructure.

---

## 2. Who we are

**Tech Cachet, LLC** develops Jira Cloud apps.

**Contact & Support:** [techcachet@gmail.com](mailto:techcachet@gmail.com) · [Support & Security](/support)

---

## 3. Data Processing

For processing **inside your Jira Cloud tenant** to provide our apps, Tech Cachet typically acts as a **processor**. **Your organization** and **Atlassian** shape the compliance picture.

Tech Cachet may act as a **controller** for **narrow** activities (e.g. **this marketing site**, **support email**, or **our own business records**).

---

## 4. Categories of personal data (examples)

| Category | Source | Use |
|----------|--------|-----|
| **Jira issue / work item data** | Jira REST APIs | Dashboard insights, intake, and security scanning |
| **Jira user identifiers** | Jira API | Identification, audit logging, and workflow assignment |
| **Secrets & integration config** | Admin UI | Stored in **Forge `storage:app`** |
| **Invoking user context** | Forge | Who ran an action |

---

## 5. Purposes of processing

- Powering **Jira dashboard gadgets** and **issue panels**.
- Performing **security scans** (e.g., Secrets Finder) within the Atlassian perimeter.
- Maintaining **app configuration** and **entitlement** status via Forge Key-Value Store.
- Providing **support** via email.

---

## 6. Sub-processors vs. customer-configured integrations

- **Core infrastructure:** **Atlassian** (Jira Cloud, Forge runtime, Forge KVS, Marketplace billing) processes data **on your behalf**. See **[Subprocessors & Infrastructure](/subprocessors)**.
- **Customer integrations:** If you configure an app to talk to a third-party service (e.g., via a configured webhook), that processing is **your** instruction.

---

## 7. Data storage and retention

- **Jira issue data:** Remains in **Jira** under **your** control. We do not copy full issue archives to external servers.
- **Forge KVS:** Stores configuration and temporary operational data. Persists while the app is installed.
- **Support email:** ([techcachet@gmail.com](mailto:techcachet@gmail.com)): Retained for up to 2 years for routine business records, unless legal retention requires otherwise.

---

## 8. Your rights & requests

For data **in Jira**, contact your **organization admin** and **Atlassian**. For **support mail** or other records Tech Cachet holds, contact **[techcachet@gmail.com](mailto:techcachet@gmail.com)**. A published **informational** **[DPA](/dpa/)** is available. See also [Terms](/terms) and [Legal & Trust](/legal/).

---

## 9. Marketing site (techcachet.github.io)

Static hosting (e.g., **GitHub Pages**). We do **not** use advertising cookies or third-party analytics.

---

## 10. Changes

We will update the **Last updated** date when we make material changes.
