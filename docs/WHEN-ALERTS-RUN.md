# When do Linked SLA Alerts run?

**Linked SLA Alerts** (Atlassian Forge, Jira Cloud): customer-facing summary aligned with product behavior.

## Configurable SLA notifications (triggers)

- There is **no** Forge **scheduled trigger**, **cron**, or **24/7 background monitor** that polls Jira.
- Configurable rules (at risk, breached, time-left thresholds, etc.) are **evaluated when the `getLinkedIssueSlas` resolver runs**: in practice, when a user **opens or refreshes** the **Linked SLA Alerts issue panel** on the **parent** issue (the issue that owns the SLA).
- If a rule **matches** the current SLA state and **deduping** allows it, the app may post Jira comments, @mentions, and optional Slack/webhook payloads per your admin configuration. **Deduping** uses **Forge Key-Value Store (KVS)**.

## Send SLA Alert to Linked Tickets

- **Separate** from trigger evaluation: this is **on-demand** when someone uses **Send SLA Alert** / **Send SLA Alert to Linked Tickets** in the panel.

## Operational note

Teams that want timely trigger-based notifications should **open the parent issue** (or rely on **natural visits** to that issue) so the panel runs and evaluation occurs, or use **Send SLA Alert** when an immediate update is needed.

---

*Maintainer note: keep aligned with the public FAQ **“When do configured SLA alerts run?”** on [Product Documentation](https://techcachet.github.io/docs/linked-sla-alerts.html#when-do-sla-alerts-run). If the app later adds a Forge scheduled job, update this file and all customer-facing copy.*


