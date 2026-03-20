# Atlassian Marketplace — listing checklist (Linked SLA Alerts)

**For internal use** when preparing your Marketplace listing. **URLs** below assume this site is served at **`https://techcache.github.io`**—adjust if you use a custom domain.

---

## Required / typical Marketplace fields

| Item | Suggested value / location |
|------|----------------------------|
| **App name** | Linked SLA Alerts |
| **Vendor** | Tech Cache |
| **Support email** | techcache@proton.me |
| **Privacy policy URL** | `https://techcache.github.io/privacy` |
| **Documentation URL** | `https://techcache.github.io/docs/sla-link-inspector.html` |
| **EULA / legal** | Link **Terms**: `https://techcache.github.io/terms` (or Atlassian’s EULA flow if you use it—**counsel**) |
| **Paid app** | Set **pricing** in Partner Center; clarify **merchant of record** (usually Atlassian for Marketplace) with **counsel** and align **Terms §3** |

---

## Strongly recommended

| Item | Notes |
|------|--------|
| **Security / trust** | Short “Security practices” blurb in listing; link **Privacy §8** or add a dedicated `security.md` later |
| **Subprocessors** | Link `https://techcache.github.io/subprocessors` in listing or partner questionnaire |
| **DPA** | Process for EU/UK B2B—contact email in **Terms** and **Privacy** |
| **Screenshots / video** | Panel, admin config, Slack sample (no real customer PII) |
| **Version & scopes** | Keep **Forge `manifest.yml`** in sync with **Privacy §7** and questionnaire |

---

## Disclosure snippets (copy-paste starters—verify against your manifest)

**What the app does (short):**  
Linked SLA Alerts runs on **Atlassian Forge**. It reads **parent issue SLA** and **linked issue** data in Jira Cloud, shows context in the issue panel, can **post comments** and **@mentions** on linked issues, and can send **optional** notifications to **Slack** or **customer-configured webhooks** when SLA rules fire. Configuration and secrets (e.g. Slack token) are stored in **Forge app storage**.

**Where data is processed:**  
Primarily **Atlassian (Jira Cloud + Forge)**. Data is sent to **Slack** or **other HTTPS endpoints** only when the **customer** configures those integrations.

**Permissions (illustrative—must match `manifest.yml`):**  
`read:jira-work`, `read:jira-user`, `read:email-address:jira`, `write:jira-work`, `storage:app`, `read:request.sla:jira-service-management` (if JSM SLA is used).

---

## Repo / branding note

Internal repo or package names may still use **`sla-link-inspector`**; the **customer-facing** name is **Linked SLA Alerts**. Align Marketplace listing, docs, and support auto-replies.

---

## Inputs for your legal counsel

- This checklist + **[Privacy Policy](/privacy)** + **[Terms](/terms)**  
- **[docs/marketplace-slack-dm.md](https://github.com/TechCache/techcache.github.io/blob/main/docs/marketplace-slack-dm.md)** (Slack / DM notes; adjust repo URL if yours differs)  
- Forge **`manifest.yml`** (scopes + `external.fetch` allowlist)  
- Whether **Tech Cache** or **Atlassian** is **merchant of record** for paid listings  
- Whether you **log PII** in Forge (audit `console.log` / APM)  
- Final **governing law** placeholders in **Terms §12**

**Contact:** [techcache@proton.me](mailto:techcache@proton.me)
