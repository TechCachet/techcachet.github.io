---
layout: default
title: Privacy Policy
permalink: /privacy/
---

# Privacy Policy

**Last updated:** March 2026  

**App:** Linked SLA Alerts (Atlassian Forge app for Jira Cloud).

**Publisher:** Tech Cache.

This Privacy Policy describes how Linked SLA Alerts accesses, uses, stores, and shares information when a customer installs and uses the app in their Jira Cloud site. It also briefly describes our marketing site (this site). **This document supports transparency and Marketplace review; it is not legal advice—involve counsel for DPA wording, EU/UK roles, and enterprise procurement.**

---

## 1. Summary

- Linked SLA Alerts runs on **Atlassian Forge**. Core processing and **Forge app storage (Key-Value Store)** are on **Atlassian’s infrastructure**. Tech Cache does **not** operate **long-lived application servers** that host the app’s core logic or store Jira issue bodies for routine operation **as of the last updated date**. If we add **optional external backends** (for example Forge Remote or other services) later, we will **update this policy** and relevant Marketplace materials.
- The app reads Jira **issue**, **link**, and (where applicable) **SLA** data to power the issue panel, **comments**, **@mentions**, and **optional** notifications via **Slack** or **customer-configured HTTPS webhooks** (e.g. email automation).
- **Personal data** is processed where needed for those features—including **Jira account identifiers**, **display names**, **email addresses** when exposed to the app by Jira for permitted APIs, and **work content** in issues referenced in messages.
- **Data leaves** Atlassian’s Jira/Forge boundary when **your organization** enables integrations to **allowlisted** destinations (Slack, Zapier/Make, etc.—see **`external.fetch`** in **`manifest.yml`**). That is **customer-controlled**, not a fixed Tech Cache “data pipeline.”
- **Billing** for Marketplace apps is typically handled by **Atlassian** (and its payment partners) under **their** terms. **Payment card data** and checkout for the Marketplace subscription are handled by **Atlassian** (or its payment partners)—**not** collected or stored by Linked SLA Alerts in the app.
- **Location / transfers:** Processing on **Forge** and in **Jira** uses **Atlassian’s** global infrastructure. Data may be processed **outside** the country where your organization is located. **Atlassian’s** product terms, privacy policy, and (where applicable) **DPA / SCCs** govern that processing—see your relationship with **Atlassian**.

---

## 2. Who we are

**Tech Cache** develops Linked SLA Alerts.  

**Contact & Support:** [techcache@proton.me](mailto:techcache@proton.me) · [Support & Security](/support)  

Linked SLA Alerts is **not directed at children** and we do **not knowingly** collect personal information from children. It is a **workplace** app for organizations using Jira.

---

## 3. Roles (controller / processor)—high level

For processing **inside your Jira Cloud tenant** to provide the app, Tech Cache typically acts as a **processor** (or subprocessor in relation to your Atlassian relationship)—**your organization** and **Atlassian** shape much of the compliance picture.  

Tech Cache may act as a **controller** for **narrow** activities (e.g. **this marketing site**, **support email**, or **our own business records**). **Confirm with counsel**, especially for EU/UK B2B and DPA needs.

---

## 4. Categories of personal data (examples)

| Category | Source | Use |
|----------|--------|-----|
| **Jira issue / work item data** | Jira REST APIs as the installed app | SLA on the **parent** issue, linked keys, summaries, fields for comments/templates; **JSM request SLA** where `read:request.sla:jira-service-management` applies |
| **Jira user identifiers & profile fields** | Jira (assignee, reporter, watchers, users from custom “notify from field” rules) | @mentions, templates, Slack matching |
| **Email addresses** | Jira user/email APIs and issue expand (subject to visibility) | Slack **users.lookupByEmail** and related flows; optional **static** addresses in admin config; webhook payloads **you** configure |
| **Slack member IDs** | Admin mapping and/or self-service from the issue panel | DMs and mentions **without** email for mapped users |
| **Secrets & integration config** | Admin UI | Slack bot token, webhook URLs, channel IDs, templates, triggers—stored in **Forge `storage:app`** |
| **Forge Key-Value Store** | Runtime | Admin config, dedupe keys, Slack ID map, Marketplace license status used for entitlement checks |
| **Invoking user context** | Forge / `asUser` where used | Who ran an action; test flows (e.g. **/myself**) |

We do **not** describe a **bulk export** of your entire Jira database or a **continuous off-site replica** of Jira; processing is **event-driven** around SLA/linked-issue flows and configuration.

---

## 5. Purposes of processing

- Show **linked issues** and **SLA** context in the **issue panel**.  
- **Post comments** on linked issues (including optional **@mentions**).  
- **Notify** recipients when SLA rules fire—via **Jira**, **Slack** (channel or DM), or **webhook** payloads.  
- **Match** Jira users to Slack (**email** and/or **Slack member ID**).  
- **Deduplicate** notifications (KVS).  
- **Marketplace** entitlement checks (e.g. to show upgrade prompts or restrict features when no active paid license in production).  
- **Persist** admin and permitted user settings.

We do **not** use personal data for **solely automated decisions** that produce **legal or similarly significant effects** about individuals (as that phrase is used in some privacy laws). SLA notifications and routing are **operational alerts** based on **your** Jira configuration and rules.

---

## 6. Subprocessors vs. customer-configured integrations

- **Subprocessors / core infrastructure:** **Atlassian** (Jira Cloud, Forge runtime, Forge KVS, Marketplace billing integration) processes data **on your behalf** when you use the app. See **[Subprocessors & Infrastructure](/subprocessors)**.  
- **Customer-configured integrations:** When you enable **Slack**, **Zapier/Make**, or another integration whose **API host** is on the app’s **`external.fetch`** allowlist, **you** choose among those permitted destinations. Data is sent **under your configuration**; those providers process data under **their** terms. They are **not** “Tech Cache subprocessors” in the same sense as Atlassian, though your counsel may treat them as **your** subprocessors.

---

## 7. Email address access

**Why the app accesses email:** Primarily to **match Jira users to Slack accounts** (e.g. Slack **users.lookupByEmail**) when DMs or Slack delivery depend on email, and to include **recipient-related fields** in **email-style webhook** payloads **you** enable.

**How:** Through **Jira Cloud REST APIs** permitted by install scopes (including **`read:email-address:jira`** where declared). Visibility of email is controlled by **Atlassian**, **organization**, and **user** settings; some users may have **no email** visible to the app.

**Stored vs. transient:**

- **Transient / in-memory:** Email values read from Jira during a resolver or job may be used only for that operation (e.g. a Slack API call) and are **not** written to a Tech Cache–operated database outside Forge.  
- **Stored in Forge KVS:** **Admin configuration** you save—such as optional **“always notify”** email lists or similar fields—is **persisted** in **Forge app storage** as part of **your** settings blob.  
- **Not stored by Tech Cache off-Forge:** We do **not** operate a separate Tech Cache database of Jira issue content or user emails for core app operation as described here.

---

## 8. Slack: webhooks, bot/token features, and direct messages

| Configuration | What happens | Data that may leave Atlassian |
|---------------|--------------|-------------------------------|
| **Incoming webhook** | POST to URL you provide | Message text, issue keys, links, formatting you configured |
| **Bot token + channel** | API calls to Slack with your token | Channel ID, message payload; token sent in **Authorization** (HTTPS) |
| **Direct messages (DMs)** | Slack API to open DM / post as **your** Slack app | Issue/SLA text you put in templates; **Slack user IDs**; may use **email lookup** or **admin/user Slack ID map** |

DMs appear as messages from **your** Slack app/bot. Content may identify individuals through **work context** (assignments, issue keys). **Admin** configures defaults; **users** may map their own Slack ID where the product allows. **Admins** can **turn off** self-service Slack ID linking so that only **admin-managed** mappings apply (product setting).

---

## 9. Admin-configured integrations (email / webhooks)

If you enable an **email or automation webhook** via an integration whose **endpoint hostname** is on the app’s Forge **`external.fetch`** allowlist (e.g. **Zapier** or **Make**—not arbitrary URLs), the app sends **HTTPS POST** requests to that endpoint when notifications fire. JSON bodies typically include **event type**, **parent and linked issue keys**, **SLA status and timing**, **message and subject** text from your templates, and **recipient-related fields** where your settings supply them. **Only configure endpoints you trust.** Outbound calls are limited to hostnames on the Forge **`external.fetch`** allowlist in the **published** **`manifest.yml`** for your app version (exact entries can change between releases—**check the manifest** for the current list). Illustrative categories include **Atlassian** product domains (e.g. `*.atlassian.net`), **Slack** (`hooks.slack.com`, `slack.com`), **Zapier** (`hooks.zapier.com`), and **Make** regional webhook hosts (e.g. `hook.eu1.make.com`, `hook.us1.make.com`—**subject to change** in the manifest).

---

## 10. When data is sent outside Atlassian (overview)

| Destination | What may be sent | Control |
|-------------|------------------|---------|
| **Slack** | Messages, API payloads (may include email in lookup requests, user IDs, tokens in headers) | Your Slack app, webhook, token, channel, DM settings |
| **Zapier / Make** (and any other provider whose **hostname** appears on the **`external.fetch`** allowlist in **`manifest.yml`**) | JSON webhook body per your config | Destination **you** choose **only** among allowlisted hosts (see §9); not a free-form “any HTTPS URL” integration |
| **Jira Cloud** (`*.atlassian.net`) | Normal API traffic | Core product |

**Forge KVS** holds app settings and operational keys—not a separate Tech Cache issue warehouse.

---

## 11. App permissions (Forge / Jira scopes)

Exact scopes and **external fetch** allowlist are in your **`manifest.yml`** (keep this policy and the Marketplace listing aligned). Illustrative permissions:

- `read:jira-work`, `read:jira-user`, `read:email-address:jira`, `write:jira-work`, `storage:app`, `read:request.sla:jira-service-management` (if JSM SLA is used)

---

## 12. Security practices (summary)

- **HTTPS** to Slack and customer webhooks.  
- **Secrets** in **Forge app storage**; **encryption at rest** per **Atlassian**; tokens **masked** in browser-facing API responses where designed; **clear** in admin UI where offered.  
- **Logging:** Aim to avoid logging **secrets** or unnecessary personal data in production—**verify** in your deployment.  
- **Least privilege:** Integrations are **opt-in** via admin configuration.

We **do not** claim SOC 2, ISO 27001, or other certifications **unless** you have actually achieved them and list them accurately.

---

## 13. Data storage and retention (including issue content)

- **Issue bodies, comments, and history** remain in **Jira** under **your** and **Atlassian’s** controls. The app does **not** copy full issue archives to Tech Cache servers for routine operation.  
- **Forge KVS:** Configuration, dedupe keys, Slack ID mappings, and similar **persist while the app is installed** (subject to Atlassian’s uninstall/lifecycle behavior).  
- **Uninstall / subscription end:** Access and app storage follow **Atlassian** processes; disable integrations by removing config before uninstall if your policy requires.  
- **Support email** ([techcache@proton.me](mailto:techcache@proton.me)): Messages are used to respond to you and for **routine business records**. We retain them **as long as needed** for **support**, **record-keeping**, and **legal obligations**—**often up to about 24 months** in ordinary cases, unless a longer period is required by law or an open thread reasonably requires keeping the correspondence. You may ask us to delete support content **where applicable** by contacting the same address.

---

## 14. Customer controls

- **Jira / Atlassian:** Site admin controls install, scopes upgrade, and org policies (including **email visibility**).  
- **App admin:** Triggers, templates, Slack/webhook URLs, tokens, mention rules, optional static emails.  
- **End users:** Where the product allows, self-service Slack ID for DM fallback—unless **admins** disable self-service mapping (admin-only mode). Admins may override via mapping.  
- **Disabling outbound data:** Remove or clear Slack/webhook configuration and tokens in the admin UI.

---

## 15. Your rights & requests

For data **in Jira**, contact your **organization admin** and **Atlassian**. For **support mail** or other records Tech Cache holds, contact **[techcache@proton.me](mailto:techcache@proton.me)**. EU/UK business customers may request a **DPA**—see [Terms](/terms) and [Legal & Trust](/legal/).

---

## 16. Marketing site (techcache.github.io)

Static hosting (e.g. **GitHub Pages**); may generate **technical/CDN logs**. We do **not** intend to use **advertising cookies** or third-party **analytics** on this site **as of the last updated date**; if that changes, we will update this policy.

---

## 17. Changes

We will update the **Last updated** date when we make material changes. Significant changes to how the app handles data will also be reflected in Marketplace listing notes or documentation when practical.

---

## 18. Contact

**Tech Cache** — [techcache@proton.me](mailto:techcache@proton.me) · [Support & Security](/support) · [Legal & Trust](/legal/)
