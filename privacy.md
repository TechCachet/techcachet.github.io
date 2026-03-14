# Privacy Policy
Last updated: March 2026

Tech Cache ("we", "our", or "us") develops tools designed to enhance workflows within Atlassian products such as Jira and Confluence.

Tech Cache respects your privacy and is committed to protecting customer data. This Privacy Policy explains how the Linked SLA Alerts app accesses and processes information.

## Information We Access

Linked SLA Alerts accesses limited information from Jira issues in order to notify linked issues of SLA status and expiry, post comments and @mentions on linked tickets, and send optional Slack or email notifications.

This may include:

• Issue keys (parent and linked issues)  
• Issue link relationships  
• SLA status and expiration information (from the parent issue only)  
• Assignee, reporter, and watcher information (used only for @mentions as configured by the administrator)  
• Users from configurable custom fields (e.g. Request Participants) when the admin enables “notify from linked-ticket fields” for @mentions  
• Issue metadata necessary to post comments and relay SLA status to linked tickets  

The app only accesses data that the Jira user already has permission to view.

## Personal Data

Linked SLA Alerts does **not collect, store, or process personal data outside of Atlassian systems.**

The app does not maintain external databases or store user information.

Any data accessed by the app is processed temporarily within Atlassian's Forge platform and is not retained by Tech Cache.

## Data Storage

Linked SLA Alerts does not store customer data outside of Atlassian infrastructure.

The app stores configuration (for example, triggers, notification channels, and message templates) and temporary state (for example, to avoid duplicate notifications) within Atlassian Forge Key-Value Store. If you configure Slack using a Bot token, that token is also stored in Forge KVS; Atlassian encrypts data at rest. The token is not sent to the browser (it is masked in API responses) and can be cleared at any time via “Clear saved token” in the app’s Configurations page. No data is sent to or stored on Tech Cache servers.

All processing occurs within Atlassian Forge functions.

## Admin-Configured Integrations

If you configure Slack (via webhook or Bot token + channel) or email webhook in the app’s Configurations, the app will send notification content to those endpoints. That content may include issue keys, clickable links to Jira issues, and user names used in @mentions or message templates. Use of that data is governed by those services’ privacy policies (for example, Slack, Zapier, Make).

## Third-Party Sharing

Tech Cache does not sell, rent, or distribute customer data to third parties.

## Security

The application runs entirely on Atlassian Forge infrastructure, which provides security controls, access management, and data isolation.

## Data Retention

Linked SLA Alerts does not retain customer issue data. Configuration settings remain stored within Atlassian Forge storage only while the application is installed.

## Changes to this Policy

We will update the Last updated date at the top of this page when changes are made. Continued use of the app after changes constitutes acceptance.

## User Rights

Users may contact us at [Tech Cache](mailto:techcache@proton.me) to request information about data the app has accessed or to request deletion.

## Contact

If you have questions about this policy, contact:

[Tech Cache](mailto:techcache@proton.me)
