# Subprocessors & infrastructure

**Last updated:** March 2026  

This page summarizes **infrastructure and services** relevant to **Linked SLA Alerts** (Jira Cloud / Forge). It supports **[Privacy Policy](/privacy)** disclosures. **Your counsel** should classify vendors (processor vs. subprocessor vs. conduit) for your DPA and ROPA.

---

## Core platform (always involved)

| Provider | Role | Notes |
|----------|------|--------|
| **Atlassian** | Jira Cloud, **Forge** runtime, **Forge app storage (KVS)**, Marketplace billing integration | Customer relationship with Atlassian; encryption at rest for Forge storage per Atlassian docs |

App **logic** and **configuration storage** for Linked SLA Alerts run on **Forge**; Tech Cache does **not** operate separate long-lived **application servers** for that core processing as described in the Privacy Policy.

---

## Optional destinations (customer-configured)

These apply **only** when **your organization** configures integrations in the app:

| Provider / type | Role | Notes |
|-----------------|------|--------|
| **Slack** | Notification delivery, user lookup | Data and message content you route to Slack are subject to **Slack’s** terms and privacy policy |
| **Zapier, Make, or similar** | Webhook receiver for email/automation flows | Depends on URL **you** configure |
| **Customer HTTPS endpoint** | Webhook receiver | **You** control the host and processing |

Tech Cache **does not** sell personal data from the app to data brokers.

---

## Tech Cache–operated surfaces

| Surface | Role | Notes |
|---------|------|--------|
| **techcache.github.io** (static marketing site) | Hosting via **GitHub Pages** | May process **technical** logs (e.g. CDN/host); no Jira issue database here for app operation |
| **Support email** ([techcache@proton.me](mailto:techcache@proton.me)) | Support mailbox (e.g. **Proton Mail**) | Retention per **your** internal policy—**document** in Privacy Policy if you keep copies |

---

## Changes

Update this page when you add **new outbound hosts** (manifest allowlist), **analytics**, or **support tools**. Link from the **[Privacy Policy](/privacy)** and Atlassian Marketplace listing as needed.

**Contact:** [techcache@proton.me](mailto:techcache@proton.me)
