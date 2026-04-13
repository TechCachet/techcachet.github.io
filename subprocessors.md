---
layout: default
title: "Subprocessors & Infrastructure"
permalink: /subprocessors/
---

# Subprocessors & Infrastructure

**Last updated:** April 2026

This page supports **[Privacy Policy](/privacy)** disclosures for all **Tech Cachet** apps. 

---

## A. Core Platform (App Runtime)

Our apps run **entirely on Atlassian Forge**. We do not operate separate long-lived application servers or external databases for core app logic.

| Provider | Role | Notes |
|----------|------|--------|
| **Atlassian** | **Jira Cloud**, **Forge** runtime, **Forge app storage (KVS)**, **Marketplace** licensing/billing integration | Global Atlassian infrastructure |

---

## B. Business Services

These services support the **Tech Cachet** company operations but do not process your Jira issue data.

| Provider | Role | Relation to app data |
|----------|------|----------------------|
| **GitHub Pages** | Hosts **techcachet.com** | No Jira data access |
| **Google (Gmail)** | Support mailbox ([support@techcachet.com](mailto:support@techcachet.com)) | Contains only data you include in support emails |

---

## C. External Integrations

Our current apps (such as Audit & Risk Insights) are **network-isolated** and do not transmit data to third-party services. If we add optional integrations in the future, they will be listed here.

**Contact:** [support@techcachet.com](mailto:support@techcachet.com) · [Support & Security](https://techcachet.com/support/)
