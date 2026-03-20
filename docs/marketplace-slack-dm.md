# Marketplace, Slack & DMs — notes for legal / security review

**Linked SLA Alerts** may send messages to **Slack** (channels or DMs) when a customer configures Slack in the app admin UI. Use this note together with:

- Site **[Privacy Policy](/privacy)** (especially §6, §9)  
- **[Subprocessors & infrastructure](/subprocessors)**  
- Forge **`manifest.yml`** (scopes + `external.fetch` allowlist)  
- **[Marketplace listing checklist](/marketplace)**  

## Slack-specific disclosures

- **Bot / app identity:** Messages appear as the customer’s Slack app/bot, not as Tech Cache impersonating the user.  
- **Content:** Payloads may include **issue keys**, **SLA status text**, **links to Jira**, and **@mentions** consistent with templates—i.e. **work context** that may identify individuals.  
- **User matching:** The app may use **email** (via Jira APIs, where visible) and/or **Slack member IDs** supplied by admins or self-service from the issue panel. Not every Jira user may resolve in Slack.  
- **Secrets:** **Bot tokens** and **webhook URLs** are customer-supplied and stored in **Forge app storage**; customers are responsible for Slack app configuration and revocation.

If you publish a **separate Slack app directory listing**, use the same **Privacy Policy URL** and align copy with Slack’s disclosure requirements.

---

*This file is operational guidance, not legal advice.*
