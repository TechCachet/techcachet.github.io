# Privacy Policy

**Last updated:** March 2026  

**App:** Linked SLA Alerts (Atlassian Forge app for Jira Cloud)  
**Publisher:** Tech Cache  

This Privacy Policy describes how Linked SLA Alerts accesses, uses, stores, and shares information when a customer installs and uses the app in their Jira Cloud site. It also briefly describes our marketing site (this site). **This document is for transparency and customer trust; it is not legal advice—please involve counsel for DPA wording, EU/UK roles, and enterprise procurement.**

---

## 1. Summary

- Linked SLA Alerts runs on **Atlassian Forge**. Core processing and **Forge app storage (Key-Value Store)** live on **Atlassian’s infrastructure**, not on servers operated by Tech Cache for app logic.
- The app reads Jira issue, link, and (where applicable) **SLA** data to show status in the issue panel, post **comments** on linked issues, optionally **@mention** users, and send **optional** notifications via **Slack** or **customer-configured webhooks** (e.g. email automation).
- **Personal data** (such as account identifiers, display names, email where exposed by Jira for the app, and content in issues) is processed **only as needed** for these features and **only within the permissions** granted at install and by your Jira configuration.
- **Data leaves Atlassian’s Jira/Forge boundary** when **you** turn on integrations and provide endpoints or tokens (e.g. Slack, Zapier/Make, or a custom HTTPS URL). Tech Cache does **not** operate a separate customer-issue database for routine app operation as described here.

**Billing:** If you obtain the app through the **Atlassian Marketplace** as a **paid** app, **payment and subscription records** are handled by **Atlassian** (and any payment partners they use) under their terms and privacy policy—not described in detail in this app policy.

---

## 2. Who we are

**Tech Cache** develops Linked SLA Alerts.  

**Contact:** [techcache@proton.me](mailto:techcache@proton.me)  

**Support:** Same email; see also [Marketplace & listing information](/marketplace).

---

## 3. Roles (controller / processor)—high level

For processing that happens **inside your Jira Cloud tenant** to provide the app (reading issues, writing comments, storing app configuration in Forge storage, calling Slack/webhooks **you** configure), Tech Cache typically acts as a **processor** (or subprocessor on behalf of your use of Atlassian’s platform)—**your organization** and **Atlassian** determine much of the overall compliance picture.  

Tech Cache may act as a **controller** for a **narrow** set of activities, such as **operating this marketing site**, **handling support emails you send us**, or **records required for our own business** (subject to what we actually collect—e.g. support mailbox). **Confirm roles and DPA requirements with legal counsel**, especially for EU/UK customers.

---

## 4. Categories of personal data (examples)

| Category | Source | Use |
|----------|--------|-----|
| **Jira issue / work item data** | Jira REST APIs as the installed app | SLA status on the **parent** issue, linked issue keys, summaries, fields needed for comments and templates; **JSM request SLA** where the `read:request.sla:jira-service-management` scope applies |
| **Jira user identifiers & profile fields** | Jira (e.g. assignee, reporter, watchers, users resolved from custom fields for “notify from field”) | **@mentions**, display in messages, matching users to Slack where configured |
| **Email addresses** | Jira user / email APIs (subject to Atlassian and org visibility settings) | **Slack users.lookupByEmail** (when used), optional **email-related webhook** payloads you configure |
| **Slack member IDs** | Admin configuration and/or **self-service** mapping from the issue panel | Routing DMs or mentions in Slack without email where configured |
| **Secrets & integration config** | Admin UI (Slack bot token, webhook URLs, channel IDs, “always notify” emails, templates, triggers) | Calling Slack or customer endpoints; stored in **Forge `storage:app`**—treat as **customer-controlled secrets** |
| **App configuration** | Admin UI | Triggers, templates, mention rules, channel choices, license-related flags as implemented |
| **Forge Key-Value Store** | Runtime | Admin config blob, per-user Slack ID map (self-service), **deduplication / state keys** (e.g. to avoid repeat alerts for the same transition) |
| **Invoking user context** | Forge context / `asUser` where used | e.g. who ran a test action; resolving **/myself** in test flows |

We do **not** describe here a **bulk export** of your entire Jira database or a **continuous off-site replica** of Jira content; processing is **driven by** SLA / linked-issue flows and admin actions as implemented.

---

## 5. Purposes of processing

- Display **linked issues** and **SLA** context in the **issue panel**.
- **Post comments** on linked issues when configured (including optional **@mentions**).
- **Notify** configured recipients when the parent SLA meets rules you set (e.g. at risk, breached, time thresholds)—via **Jira comment**, **Slack** (channel/DM), or **email-via-webhook** payloads.
- **Match** Jira users to Slack (by **email** and/or **Slack member ID** you configure).
- **Deduplicate** alerts using KVS keys so the same event does not spam recipients.
- **Marketplace licensing** checks as implemented in the app.
- **Persist** admin (and permitted user) configuration.

---

## 6. When data is sent outside Atlassian (customer-controlled)

Data **leaves** Atlassian’s Jira/Forge environment for app features **only when you enable integrations** and supply destinations. Examples:

| Destination | What may be sent | Customer control |
|-------------|------------------|------------------|
| **Slack** (`slack.com`, `hooks.slack.com`, etc.) | Message text (e.g. mrkdwn), issue keys, links; API calls may use **email** for lookup and **Slack user IDs**; **bot token** in `Authorization` | You provide webhook URL and/or bot token, channel, DM settings |
| **Zapier / Make** (or similar; hostnames depend on URL you paste) | **JSON** payload for email/automation (event, issue keys, status, recipient metadata, message, subject—**as implemented**) | You paste the webhook URL |
| **Your HTTPS webhook** | Similar JSON pattern if the app supports arbitrary URL (**confirm validation** in your deployment) | You configure the URL |
| **Jira Cloud** (`*.atlassian.net`) | Standard API access under install scopes | Core product—not optional |

There is **no separate Tech Cache database** for routine issue content in this architecture; **Forge KVS** holds app settings and operational state as described.

See also: **[Subprocessors & infrastructure](/subprocessors)**.

---

## 7. App permissions (Forge / Jira scopes)

The app’s **exact** scopes and **external fetch allowlist** are defined in the app’s **`manifest.yml`** in the Forge project (they may change between versions; the Marketplace listing should stay in sync). For transparency, the app is designed to use permissions along the lines of:

- `read:jira-work` — read issues, links, fields needed for SLA and comments  
- `read:jira-user` — resolve users for mentions and Slack matching  
- `read:email-address:jira` — read email for Slack email lookup and related flows (**subject to Jira/org visibility**)  
- `write:jira-work` — post comments and related writes  
- `storage:app` — Forge Key-Value Store for configuration and dedupe state  
- `read:request.sla:jira-service-management` — **JSM** request SLA where applicable  

**External fetch** hosts must match the manifest allowlist (e.g. Atlassian, Slack, automation providers)—**update this policy and the listing** if you add hosts.

---

## 8. Security practices (summary)

- **Transport:** HTTPS to Slack and customer webhooks where applicable.  
- **Secrets:** Slack bot tokens and webhook URLs are **customer-supplied**; stored in **Forge app storage**. **Encryption at rest** for Forge storage is provided by **Atlassian’s platform**; we design the app so tokens are **masked** in API responses to the browser and can be **cleared** in the admin UI (e.g. “Clear saved token”).  
- **Logging:** We aim **not** to log secrets or unnecessary personal data in production; **verify** in your codebase before claiming in audits.  
- **Least privilege:** Slack, email webhook, and aggressive automation are **opt-in** via admin configuration.  
- **Admin vs. end user:** **Admins** configure global behavior; the issue panel may allow **self-service** Slack ID mapping, merged with admin rules (**admin configuration typically overrides** where implemented—confirm in product docs).

A **full security whitepaper** is not a substitute for customer **pen tests** and **Atlassian’s** shared responsibility model.

---

## 9. Email visibility & Slack matching

Visibility of **email addresses** in Jira is controlled by **Atlassian**, your **organization**, and **user** settings. The app requests email access only for **stated features** (e.g. Slack lookup). Some users may **not** be resolvable by email; behavior should be documented honestly in support docs.

**Slack DMs** appear as messages from **your** Slack app/bot; content may include **issue keys** and **SLA text** derived from tickets—treat as **work context** that may identify individuals.

---

## 10. Retention & deletion

- **Forge KVS** (admin config, dedupe keys, self-service Slack map): retained **while the app is installed** and as needed for operation; **uninstall** and **Atlassian’s processes** for app data apply. Tech Cache does **not** need to retain issue bodies on our own servers for core features described here.  
- **Support** emails or **manual** records outside Forge: describe your actual practice (e.g. deleted after ticket closed)—**update this section** if you keep logs.  
- **Analytics** on this marketing site: if you add analytics later, update this policy and consider a **cookie notice**.

---

## 11. Your rights & requests

Depending on jurisdiction, users may have rights to access, correct, delete, or restrict processing of personal data. For data **inside Jira**, your **organization admin** and **Atlassian** are often the first contact. For data Tech Cache holds as controller (e.g. support mail), contact **[techcache@proton.me](mailto:techcache@proton.me)**.  

**EU/UK:** Business customers may request a **Data Processing Agreement (DPA)**—see [Terms of Service](/terms) and contact us; counsel should finalize wording.

---

## 12. Marketing site (techcache.github.io)

This static site may use **essential** hosting/CDN behavior. We do **not** intend to use **advertising cookies** or third-party **analytics** on this site **as of the last updated date**; if that changes, we will update this policy.

---

## 13. Changes

We will update the **Last updated** date when we make material changes. **Continued use** of the app after changes may constitute acceptance as described in your customer agreement or Atlassian Marketplace terms—**counsel** should align wording with how you ship updates.

---

## 14. Contact

**Tech Cache** — [techcache@proton.me](mailto:techcache@proton.me)
