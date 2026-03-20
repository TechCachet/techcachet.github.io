# Atlassian Marketplace — listing checklist (Linked SLA Alerts)

**For internal use** when preparing your Marketplace listing. **URLs** below assume this site is served at **`https://techcache.github.io`**—adjust if you use a custom domain.

---

## Required / typical Marketplace fields

| Item | Suggested value / location |
|------|----------------------------|
| **App name** | Linked SLA Alerts |
| **Vendor** | Tech Cache |
| **Support email** | techcache@proton.me |
| **Support / security page** | `https://techcache.github.io/support` (optional but strong for trust) |
| **Privacy policy URL** | `https://techcache.github.io/privacy` |
| **Documentation URL** | `https://techcache.github.io/docs/sla-link-inspector.html` |
| **Security / trust overview** | `https://techcache.github.io/security-review` (Forge architecture + optional integrations—**no fake certifications**) |
| **EULA / legal** | Link **Terms**: `https://techcache.github.io/terms` (or Atlassian’s EULA flow if you use it—**counsel**) |
| **Paid app** | Set **pricing** in Partner Center; clarify **merchant of record** (usually Atlassian for Marketplace) with **counsel** and align **Terms §3** |

---

## Strongly recommended

| Item | Notes |
|------|--------|
| **Security / trust** | Link **`/security-review`**; Privacy Policy **§12** (security summary); subprocessors page |
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

The GitHub repository may remain **`sla-link-inspector`** while the **Marketplace and in-Jira name** is **Linked SLA Alerts**. That is normal; avoid renaming the repo unless you are ready to retool CI, links, and clones. **Do** keep customer-facing copy and support replies on **Linked SLA Alerts**.

**MIT `LICENSE` in the public repo** vs. **paid Marketplace** — see **[Licensing note](/licensing)** and the app repo’s **`sla-link-inspector/docs/LICENSING-NOTE.md`**. Do not change the license file without counsel.

---

## Inputs for your legal counsel

- This checklist + **[Privacy Policy](/privacy)** + **[Terms](/terms)**  
- **[docs/marketplace-slack-dm.md](https://github.com/TechCache/techcache.github.io/blob/main/docs/marketplace-slack-dm.md)** (Slack / DM notes; adjust repo URL if yours differs)  
- Forge **`manifest.yml`** (scopes + `external.fetch` allowlist)  
- Whether **Tech Cache** or **Atlassian** is **merchant of record** for paid listings  
- Whether you **log PII** in Forge (audit `console.log` / APM)  
- Final **governing law** placeholders in **Terms §12**

**Contact:** [techcache@proton.me](mailto:techcache@proton.me)
