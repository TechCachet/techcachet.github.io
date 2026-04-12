---
layout: default
title: "Data Processing Agreement (DPA)"
permalink: /dpa/
---

# Data Processing Agreement

**Tech Cachet** (Atlassian Forge apps for Jira Cloud)

**Effective date:** Upon installation of any Tech Cachet app.

---

## 1. Parties

This DPA is entered into between:

- **Controller:** The organization that installs and uses Tech Cachet apps (**“Customer”**).  
- **Processor:** **Tech Cachet, LLC**, provider of the Apps (**“Tech Cachet”**).

---

## 2. Scope and purpose

This DPA applies where Tech Cachet processes personal data on behalf of the Customer in connection with the Customer’s use of any Tech Cachet app built on **Atlassian Forge**. 

Our apps provide visibility, workflow analysis, and security scanning for **Jira**, including:
- **Evaluating** issue state and metadata to generate dashboard insights.
- **Scanning** issue content for security risks (e.g., Secrets Finder).
- **Processing** app configurations stored within the Atlassian Forge environment.

---

## 3. Description of processing

### 3.1 Categories of data subjects

Jira users associated with analyzed issues, including assignees, reporters, and watchers.

### 3.2 Categories of personal data processed

The App minimizes data processing to provide its core functionality. We do **not** persist or store Jira user profiles or email addresses on Tech Cachet-managed servers.

| Data type | Purpose | Notes |
|-----------|---------|-------|
| Jira user identifiers | Transient UI display | Not persisted by Tech Cachet |
| Jira issue metadata | Real-time analysis | Evaluated transiently; not stored off-site |
| App configuration | Persistence of settings | Stored in **Forge** secure storage |

### 3.3 Data Minimization

The App is designed to minimize the collection of personal data. Analysis happens **transiently** during active user sessions. We do **not** maintain a persistent replica of your Jira database.

### 3.4 Frequency of processing

**Event-driven**, occurring when a user interacts with the App UI (e.g., loading a dashboard gadget or opening an issue panel) or when an administrator saves app configuration.

---

## 4. Roles of the parties

- The **Customer** is the **Controller** for personal data in **Jira** that the Customer chooses to process using the App.  
- **Tech Cachet** is the **Processor** for that in-app processing.

---

## 5. Tech Cachet’s obligations

Tech Cachet agrees to:
- **Instructions:** Process personal data only on the Customer’s instructions as expressed through the App’s configuration.
- **Confidentiality:** Ensure authorized personnel are bound by confidentiality.
- **Security:** Implement technical measures appropriate to the risk (see §9).
- **Breach Notification:** Notify the Customer without undue delay after becoming aware of a personal data breach affecting Customer data processed through the App.

---

## 6. Sub-processors

Tech Cachet relies on the following sub-processors:

| Sub-processor | Purpose |
|---------------|---------|
| **Atlassian** | App runtime (Forge), infrastructure, and billing management. |

---

## 7. International transfers

Processing on **Atlassian Forge** uses Atlassian’s global infrastructure. Data transfers are governed by Atlassian’s terms and applicable standard contractual clauses (SCCs) between the Customer and Atlassian.

---

## 8. Security measures

- **Forge-native storage:** App configurations are stored in **Atlassian**-managed storage (KVS).
- **Network Isolation:** Our apps are restricted to the Atlassian perimeter and do not send data to external third-party servers.
- **Least privilege:** We only request the minimum Jira scopes required for app functionality.

---

## 9. Term and termination

This DPA is effective for the duration of the Customer’s use of the App and terminates when the App is uninstalled. Upon uninstall, data in Forge storage is handled according to Atlassian’s deletion practices.

---

## 10. Contact

**Tech Cachet**  
Email: [techcachet@gmail.com](mailto:techcachet@gmail.com)  
Website: [techcachet.github.io](https://techcachet.github.io)
