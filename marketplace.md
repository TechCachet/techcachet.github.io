# Atlassian Marketplace — listing checklist (Linked SLA Alerts)

**For internal use** when preparing your Marketplace listing. **URLs** assume **`https://techcache.github.io`**—adjust if you use a custom domain.

---

## Required / typical Marketplace fields

| Item | Suggested value / location |
|------|----------------------------|
| **App name** | Linked SLA Alerts |
| **Vendor** | Tech Cache |
| **Support email** | techcache@proton.me |
| **Support / security page** | `https://techcache.github.io/support` |
| **Privacy policy URL** | `https://techcache.github.io/privacy` |
| **Documentation URL** | `https://techcache.github.io/docs/sla-link-inspector.html` |
| **Security / trust overview** | `https://techcache.github.io/security-review.html` |
| **Legal hub** | `https://techcache.github.io/legal` (links to Terms, Privacy, Subprocessors) |
| **EULA / legal** | `https://techcache.github.io/terms` (or Atlassian’s flow if you use it—confirm with counsel) |
| **Paid app** | Set **pricing** in Partner Center; **billing** is typically through **Atlassian** per Marketplace terms |

---

## Strongly recommended

| Item | Notes |
|------|--------|
| **Security / trust** | Link **`/security-review.html`**; [Privacy Policy](/privacy) **§12** (security summary); [Subprocessors](/subprocessors) |
| **Subprocessors** | `https://techcache.github.io/subprocessors` |
| **DPA** | EU/UK B2B—contact **techcache@proton.me** (see Terms) |
| **Screenshots / video** | Panel, admin, Slack sample (no real customer PII) |
| **Scopes** | Keep **`manifest.yml`** aligned with [Privacy Policy](/privacy) **§11** and the questionnaire |

---

## Disclosure snippets (verify against your `manifest.yml`)

**What the app does (short):**  
Linked SLA Alerts runs on **Atlassian Forge**. It reads **parent issue SLA** and **linked issue** data in Jira Cloud, shows context in the issue panel, can **post comments** and **@mentions** on linked issues, and can send **optional** notifications to **Slack** or **customer-configured HTTPS webhooks** when SLA rules fire. Configuration and secrets (e.g. Slack token) are stored in **Forge app storage**.

**Where data is processed:**  
Primarily **Atlassian (Jira Cloud + Forge)**. Data is sent to **Slack** or **other HTTPS endpoints** only when the **customer** configures those integrations.

**Permissions (illustrative—must match `manifest.yml`):**  
`read:jira-work`, `read:jira-user`, `read:email-address:jira`, `write:jira-work`, `storage:app`, `read:request.sla:jira-service-management` (if JSM SLA is used).

---

## Naming (Marketplace vs. internal)

**Customer-facing name:** **Linked SLA Alerts** (Marketplace listing, Jira UI, support, this site).  

An internal development repository may use a different **codename** (e.g. `sla-link-inspector`). That does **not** change the product name customers see. Keep all public copy on **Linked SLA Alerts**.

---

## Inputs for legal review

- [Privacy Policy](/privacy) · [Terms of Service](/terms) · [Legal information](/legal) · [Subprocessors](/subprocessors)  
- [docs/marketplace-slack-dm.md](https://github.com/TechCache/techcache.github.io/blob/main/docs/marketplace-slack-dm.md) (Slack/DM notes on **this** website repo)  
- Forge **`manifest.yml`** (scopes + `external.fetch` allowlist)  
- Whether **Tech Cache** receives any **direct** customer payments or only via **Atlassian** (affects liability context in Terms)  
- Whether you **log PII** in Forge (audit `console.log` / APM)

**Contact:** [techcache@proton.me](mailto:techcache@proton.me)
