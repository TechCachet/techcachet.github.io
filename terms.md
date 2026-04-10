---
layout: default
title: Terms of Service
permalink: /terms/
---

# Terms of Service

**Last updated:** March 2026  

These Terms of Service (“**Terms**”) govern use of **Linked SLA Alerts**, a **Jira Cloud** app published by **Tech Cachet** and offered through the **Atlassian Marketplace** (including as a **paid** app).

By **installing**, **configuring**, or **using** the app, you confirm that you have authority to bind the **organization** whose Jira site the app is installed on, and you agree to these Terms. If you do not agree, do not use the app.

**Atlassian:** Atlassian’s **Marketplace Terms of Use**, **product terms**, and **privacy policies** also apply. **Billing, payment, tax, trials, renewals, cancellations, and refunds** are typically handled by **Atlassian** (or its payment partners) under **their** terms. **These Terms add to, not replace, Atlassian’s terms.** If anything here conflicts with Atlassian on **payment or Marketplace rules**, **Atlassian’s terms control** for those topics.

---

## 1. The application

**Linked SLA Alerts** runs on **Atlassian Forge**. It reads Jira **issue** and **SLA** data (including **linked issues**), may **post comments** and **@mentions** on linked issues, and may send **optional** notifications via **Slack** or **HTTPS webhooks** you configure in the admin UI. **Configurable** SLA notifications are **evaluated when someone opens or refreshes** the **Linked SLA Alerts** issue **panel** on the parent issue (not on a Forge **scheduled** trigger or background cron); **Send SLA Alert to Linked Tickets** is **on-demand** when you use that action in the panel.

**Docs:** [Product Overview](/linked-sla-alerts.html) · [Product Documentation](/docs/linked-sla-alerts.html) · [Privacy Policy](/privacy)

---

## 2. Who may install

You must be allowed to install **Marketplace apps** on your Jira Cloud site and to accept these Terms for your **organization** (for example, a site admin or authorized buyer). You must follow **Atlassian** account rules and your **own** internal policies.

---

## 3. License to use

Subject to these Terms and a **valid Marketplace entitlement** (paid subscription or **trial**, if Atlassian offers one), Tech Cachet grants your organization a **limited, non-exclusive, non-transferable, revocable** right to use the app **only** in **your** Jira Cloud site(s) for **internal business use**.

You may not: misuse the app; reverse engineer it beyond what the law allows; use it to build a competing product; strip legal notices; break the law or Atlassian’s rules; or overload systems.

---

## 4. Paid access, billing, trials, renewals, and cancellation

- **Prices and plans** are set on the **Atlassian Marketplace** (and may change for **new** purchases as Atlassian allows).  
- **Charges, invoices, refunds, and taxes** are handled under **Atlassian’s** checkout and Marketplace terms, not summarized here.  
- **Trials** follow **Atlassian’s** trial rules, if available.  
- **Renewal and cancellation** are managed in **Atlassian** account / Marketplace controls, unless you have a **separate written agreement** with Tech Cachet.  
- The app may check **Marketplace license status** through Forge (for example, `getAppContext().license`) to show or enforce paid access in **production**.

---

## 5. End of use (uninstall, expiry, breach)

Your right to use the app **ends** if you **uninstall** it, **lose** Marketplace entitlement, **Atlassian** ends the install, or you **break** these Terms. Tech Cachet may **stop offering** the app where required by law or Atlassian policy.

**When the app stops:** Features that need a **valid license** may **stop working**. Settings in **Forge** storage follow **Atlassian’s** rules for app data. **Turn off** Slack and webhooks in the admin UI if you need integrations to stop immediately. Export any configuration **your policies require** before uninstall.

---

## 6. App discontinuation

If Tech Cachet decides to **discontinue** Linked SLA Alerts, customers will be given **at least 30 days’ notice** via the **Atlassian Marketplace** listing and by **email** where we have **contact information** available.

When the app is **uninstalled**, **configuration data** stored in **Forge Key-Value Store** is **automatically deleted** by **Atlassian’s platform** according to Atlassian’s processes. **Tech Cachet does not retain customer Jira data** after the app is uninstalled.

---

## 7. Your responsibilities

You are responsible for **lawful use**, correct **configuration** (Slack, webhooks, templates, mentions), and **secrets** you enter. You must follow **privacy**, **employment**, and **industry** rules that apply to you. You must respect **Jira permissions** and **email visibility** settings.

---

## 8. Privacy

See the **[Privacy Policy](/privacy)**, **[Subprocessors & Infrastructure](/subprocessors)**, **[Data Processing Agreement (DPA)](/dpa/)** (informational; not yet reviewed by Tech Cachet’s counsel), and **[Legal & Trust](/legal/)** (index of policies and Security Overview). For **custom** DPA requests: **[techcachet@gmail.com](mailto:techcachet@gmail.com)**.

---

## 9. Support & Security

**Email:** [techcachet@gmail.com](mailto:techcachet@gmail.com) · Details: **[Support & Security](/support)**  

Report security issues **only** through that **private email** channel as described there, not via public GitHub issues or a public tracker.

We do **not** promise a specific response time unless we agree **in writing** with your organization.

---

## 10. Availability and updates

The app relies on **Forge**, **Jira**, and any **third-party services you turn on**. We do **not** promise **uninterrupted** or **error-free** operation. We may ship **updates** through the Marketplace; important changes may be noted in the listing or docs.

---

## 11. Disclaimer

**TO THE EXTENT THE LAW ALLOWS**, THE APP IS PROVIDED **“AS IS”** AND **“AS AVAILABLE.”** TECH CACHET DISCLAIMS **ALL IMPLIED WARRANTIES**, INCLUDING **MERCHANTABILITY**, **FITNESS FOR A PARTICULAR PURPOSE**, AND **NON-INFRINGEMENT**.

---

## 12. Limitation of liability

**TO THE EXTENT THE LAW ALLOWS**, TECH CACHET IS **NOT LIABLE** FOR **INDIRECT**, **SPECIAL**, **CONSEQUENTIAL**, OR **PUNITIVE** DAMAGES, OR FOR **LOST PROFITS**, **DATA**, OR **GOODWILL**, ARISING FROM USE OF THE APP.

TECH CACHET'S **TOTAL LIABILITY** FOR CLAIMS ABOUT THE APP IN ANY **12-MONTH PERIOD** IS LIMITED TO THE **GREATER OF** (A) **ONE HUNDRED U.S. DOLLARS (USD $100)** OR (B) **FEES YOU PAID DIRECTLY TO TECH CACHET** FOR THE APP IN THAT PERIOD. If you **only** pay through **Atlassian** and owe **nothing** directly to Tech Cachet, (B) is **zero**, so the cap is **USD $100**.

Some states or countries do not allow certain limits; in those cases our limits apply **only as far as the law allows**.

---

## 13. Indemnity

You will **defend and reimburse** Tech Cachet for claims caused by **your** misuse of the app, **your** Jira content, or **your** integration settings, except where Tech Cachet has engaged in **willful misconduct** (as finally decided by a court).

---

## 14. Governing law and venue

These Terms are governed by the laws of the **State of Florida**, without regard to conflict-of-law rules.

You and Tech Cachet agree that the **state and federal courts located in Hillsborough County, Florida** have **exclusive jurisdiction** over disputes arising from these Terms or the app, **except** where applicable law requires a different forum.

---

## 15. Contact

**Tech Cachet**: [techcachet@gmail.com](mailto:techcachet@gmail.com) · [Support & Security](/support)




