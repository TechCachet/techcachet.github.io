---
layout: default
title: "Subprocessors & Infrastructure"
permalink: /subprocessors/
---

# Subprocessors & Infrastructure

**Last updated:** March 2026  

This page supports **[Privacy Policy](/privacy)** disclosures for **Linked SLA Alerts**. It separates **(A)** infrastructure that always applies, **(B)** services Tech Cachet uses for **our business** (not the app runtime), and **(C)** destinations **you** configure, which are **not** Tech Cachet subprocessors in the usual sense.

**Classification (processor / subprocessor / conduit)** depends on your jurisdiction and contracts, **confirm with counsel**.

---

## A. Core platform (always involved when the app runs)

| Provider | Role | Notes |
|----------|------|--------|
| **Atlassian** | **Jira Cloud**, **Forge** runtime, **Forge app storage (KVS)**, **Marketplace** licensing/billing integration | Customer relationship with Atlassian; encryption at rest for Forge storage per **Atlassian** documentation |

**Linked SLA Alerts** app logic runs on **Forge**. Tech Cachet does **not** operate **separate long-lived application servers** that host that core logic or store Jira issue content for routine app operation as described in the Privacy Policy.

---

## B. Tech Cachet business services (not Jira app runtime)

These support **Tech Cachet the company** (website, email). They do **not** replace Forge for processing Jira issue data inside the tenant.

| Provider / surface | Role | Relation to app data |
|--------------------|------|----------------------|
| **GitHub Pages** (or similar) | Hosts **techcachet.github.io** static marketing pages | **No** Jira issue database; may have CDN/host **technical logs** |
| **Support mailbox** ([techcachet@gmail.com](mailto:techcachet@gmail.com), via **Gmail**) | Support and security reports | May contain **PII you include** in email, retention per **our** internal policy |

If you add **ticketing**, **analytics**, or **CRM**, update this table and the Privacy Policy.

---

## C. Customer-configured third parties (optional; not “Tech Cachet subprocessors”)

When **your organization** turns on integrations in the app UI, data flows **you initiate** may go to **allowlisted** destinations only, the Forge app calls **only** hostnames permitted in **`external.fetch`** in the published **`manifest.yml`** (e.g. `*.atlassian.net`, Slack, Zapier, Make regional webhook hosts, not free-form “any HTTPS URL”).

| Type | Examples | Notes |
|------|----------|--------|
| **Slack** | `slack.com`, `hooks.slack.com`, etc. | Message content, API calls, tokens **you** supply |
| **Automation / webhooks** | Zapier, Make, and other providers whose **hostnames** are on the **`external.fetch`** allowlist | JSON payloads to **permitted** endpoints **you** configure within that allowlist, see **[Privacy Policy](/privacy)** §9–10 |
| **Jira Cloud** | `*.atlassian.net` | Core APIs, not optional third party |

Tech Cachet **does not sell** personal data from the app to data brokers.

---

## Changes

Update this page when you add **manifest** fetch hosts, **analytics**, or **support tools**.

**Contact:** [techcachet@gmail.com](mailto:techcachet@gmail.com) · [Support & Security](/support) · [Legal & Trust](/legal/)



