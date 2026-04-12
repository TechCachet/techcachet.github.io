---
layout: default
title: "Data Processing Agreement (DPA)"
permalink: /dpa/
---

# Data Processing Agreement

**Tech Cachet** (Atlassian Forge apps for Jira Cloud)

**Effective date:** Upon installation of any Tech Cachet app (or first use after this version is published), unless you and Tech Cachet agree otherwise in writing.

---

## Important: read before relying on this document

- This Data Processing Agreement (**“DPA”**) is published for **transparency** and to support **EU/UK and similar** procurement conversations.  
- **Tech Cachet has not yet had this DPA reviewed by its own legal counsel.** It is **not legal advice**. **Customers should consult their own counsel** before relying on it or signing counterpart-specific versions.  
- If your organization requires a **custom-signed** DPA, contact **[techcachet@gmail.com](mailto:techcachet@gmail.com)**.

---

## 1. Parties

This DPA is entered into between:

- **Controller:** The customer or organization that installs and uses Tech Cachet apps (**“Customer”** or **“Controller”**).  
- **Processor:** **Tech Cachet**, provider of Tech Cachet apps (**“Tech Cachet”** or **“Processor”**).

---

## 2. Scope and purpose

This DPA applies where Tech Cachet processes personal data **on behalf of the Customer** in connection with the Customer’s use of any **Tech Cachet** app (the **“App”**), an Atlassian Marketplace application built on **Atlassian Forge**.

The App provides workflow, visibility, and automation features for **Jira** and **Jira Service Management**, including:

- **Evaluating** issue data and state when a user **interacts with the App’s UI** (e.g. issue panels, dashboard gadgets).
- **On-demand** actions triggered by the Customer within the App UI.  
- Posting **comments** and **@mentions** on Jira tickets when notifications are sent per the Customer’s configuration.  
- Sending **optional** notifications via **Slack** (channel posts or direct messages) when enabled by the Customer.  
- Sending **optional** payloads to **customer-configured HTTPS webhook** endpoints on the App’s Forge **`external.fetch`** allowlist (e.g. **Zapier**, **Make**) when enabled by the Customer.

---

## 3. Description of processing

### 3.1 Categories of data subjects

Jira users associated with linked (and parent) issues, including:

- Assignees  
- Reporters  
- Watchers  
- Request Participants (Jira Service Management projects, where applicable)

### 3.2 Categories of personal data processed

The App accesses and processes the following personal data **solely** to provide its core functionality:

| Data type | Purpose |
|-----------|---------|
| Jira user identifiers (e.g. display name, **account ID**, **email** where visible to the App via Jira APIs) | To **@mention** and notify the correct individuals on linked tickets; optional Slack matching |
| Jira issue metadata (e.g. issue key, SLA status, timing / expiry, fields used in templates) | To build accurate SLA messages |
| Slack bot token (Customer-provided) | To authenticate Slack delivery when enabled (stored in **Forge** secure storage; **masked** in UI where implemented) |
| Webhook / automation endpoint configuration (Customer-provided URLs on allowlisted hosts) | To deliver payloads when those channels are enabled |
| Custom message templates (Customer-configured) | To format messages for **panel-evaluated** notifications and **on-demand** Send SLA Alert |

### 3.3 Sensitive data

The App does **not** intentionally collect or process **special-category** data as defined under GDPR Article 9. Customers are responsible for ensuring that no such data is included in Jira fields or templates in ways that violate applicable law.

### 3.4 Frequency of processing

**Event-driven**, including when:

- A user **opens or refreshes** the Linked SLA Alerts **panel** on a parent issue (trigger evaluation and optional notifications, subject to deduplication in **Forge Key-Value Store**).  
- The Customer uses **on-demand Send SLA Alert**.  
- The Customer **saves** admin configuration.  
- Optional integrations (e.g. **Slack**) are invoked to deliver a notification.

The App does **not** continuously poll Jira in the background for SLA state.

### 3.5 Duration of processing

Personal data is processed for the duration of the Customer’s **active use** of the App. Upon **uninstall**, configuration and operational data held in **Forge** are handled per **Atlassian’s** platform lifecycle and deletion practices.

---

## 4. Roles of the parties

- The **Customer** is the **Controller** for personal data in **Jira** that the Customer chooses to process using the App (e.g. who is notified, which channels are on, trigger rules).  
- **Tech Cachet** is the **Processor** for that in-app processing, **except** where Tech Cachet acts as a **controller** for **narrow** activities described in the **[Privacy Policy](/privacy/)** (e.g. **support email**, **this website**).

---

## 5. Tech Cachet’s obligations

Tech Cachet agrees to:

- **Instructions.** Process personal data **only** on the Customer’s instructions as expressed through the App’s configuration and use, and as described in this DPA and applicable **Terms**, unless **EU/UK law** requires otherwise (in which case Tech Cachet will inform the Customer of that legal requirement before processing, unless prohibited).  
- **Confidentiality.** Ensure that personnel authorized to process personal data are bound by appropriate confidentiality obligations.  
- **Security.** Implement appropriate technical and organizational measures appropriate to the risk. The App runs on **Atlassian Forge**; optional details: **[Security Overview](/security/)**, **[Vulnerability disclosure policy](/vulnerability-disclosure/)**.  
- **Sub-processors.** Use sub-processors as needed to provide the App; see **Section 7**. Tech Cachet will provide **at least 30 days’** advance notice of **new** sub-processors that process personal data for the App, via **[Subprocessors & Infrastructure](/subprocessors/)** (and the website generally), unless a substitute is required for security or legal reasons (in which case notice will be given as soon as practicable).  
- **Data subject rights assistance.** Provide **reasonable** assistance to the Customer in responding to requests from data subjects, **to the extent** Tech Cachet holds or controls the relevant data and can comply without undue burden.  
- **DPIAs.** Provide **reasonable** assistance for data protection impact assessments or supervisory consultations, **taking into account** the nature of processing and information available to Tech Cachet.  
- **Personal data breaches.** Notify the Customer **without undue delay** after becoming aware of a **personal data breach** affecting Customer personal data processed through the App, where notification is required by applicable law. **Contact:** [techcachet@gmail.com](mailto:techcachet@gmail.com).  
- **Deletion / return.** After the Customer **stops** using the App or upon **written request**, Tech Cachet will **delete** or **facilitate deletion** of personal data processed through the App **as practicable**, subject to **Atlassian Forge** lifecycle and **legal retention** needs.  
- **Demonstration of compliance.** On **reasonable** request, provide information necessary to demonstrate compliance with this DPA, **no more than once per calendar year**, subject to notice and confidentiality.

---

## 6. Customer’s obligations

The Customer agrees to:

- Ensure that its use of the App and its instructions comply with applicable data protection law.  
- Ensure it has a **lawful basis** for processing personal data it instructs Tech Cachet to process through the App.  
- Provide appropriate **privacy notices** to data subjects where required.  
- Configure the App appropriately for the **sensitivity** of the data involved (including optional Slack and webhooks).

---

## 7. Sub-processors

Tech Cachet relies on the following **sub-processors** in connection with the App:

| Sub-processor | Purpose | Notes |
|---------------|---------|--------|
| **Atlassian** (Forge, Jira Cloud, Marketplace) | App runtime, **Forge** storage (e.g. configuration, tokens), Jira API access | Global Atlassian infrastructure; Customer’s relationship with Atlassian applies in parallel |
| **Slack Technologies** | Delivery of Slack messages when the Customer enables Slack | USA / global; Customer’s Slack workspace and app |
| **Customer-configured webhook host** (e.g. Zapier, Make, on allowlist) | Delivery of HTTPS payloads when the Customer enables and configures it | **Customer-selected** destination; not operated by Tech Cachet |

The Customer-configured endpoint is **entirely under the Customer’s control**. Tech Cachet does not select or operate that service.

Current list maintained at: **[Subprocessors & Infrastructure](/subprocessors/)**.

---

## 8. International transfers

The App runs on **Atlassian Forge**; processing may occur in **multiple regions** per **Atlassian’s** terms and (where applicable) **SCCs** / **DPA** between Customer and Atlassian.

Where Tech Cachet processes personal data **outside** the EEA, UK, or Switzerland **independently** of Atlassian (e.g. **support mailbox**), Tech Cachet will use **appropriate safeguards** as required by applicable law.

---

## 9. Security measures (summary)

- **Forge-native storage** for app configuration and secrets (e.g. Slack token) in **Atlassian**-managed storage, not in a separate Tech Cachet application database for core app operation as described in the **[Privacy Policy](/privacy/)**.  
- **Token masking** in configuration surfaces where implemented; Customers may **clear** tokens when the product allows.  
- **Least privilege:** Jira/Forge permissions limited to what the App requires (see published **`manifest.yml`**).  
- Further detail: **[Security Overview](/security/)** · **[Vulnerability disclosure policy](/vulnerability-disclosure/)**

---

## 10. Term and termination

This DPA is effective for the duration of the Customer’s use of the App and **terminates** when the Customer **uninstalls** or otherwise **ends** use, subject to **survival** of obligations regarding data already processed and **legal retention**.

---

## 11. Order of precedence

If the **[Terms of Service](/terms/)** and this DPA conflict **only** as to **data protection obligations** relating to processing described here, **this DPA controls** for that subject matter. **All other** matters (including liability caps, governing law, and venue) remain governed by the **Terms** unless mandatory data protection law requires otherwise.

---

## 12. Contact

**Tech Cachet**  
Email: [techcachet@gmail.com](mailto:techcachet@gmail.com)  
Phone: [813-906-9247](tel:+18139069247) (call or text)  
Website: [techcachet.github.io](https://techcachet.github.io)

---

## 13. Governing law

This DPA is governed by the laws applicable to the **underlying commercial relationship** between the parties (see **Terms of Service**), **except** where **mandatory** provisions of **EU/UK** or other applicable **data protection law** require otherwise.

---

*This DPA was last updated: **March 2026**.*  
*Tech Cachet: Practical tools for Atlassian teams.*



