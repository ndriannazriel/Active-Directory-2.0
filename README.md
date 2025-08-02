# Active Directory Security & Automation Project

This project focuses on building a simulated, end-to-end security environment to demonstrate the principles of threat detection and automated response within an Active Directory environment. The core workflow involves establishing a small-scale corporate network, monitoring it for security threats using a SIEM, and automatically responding to those threats using a SOAR platform.

---

### Project Goals

The primary objectives of this project are to:

* **Establish a Foundational Environment:** Create a functional Active Directory domain with a domain controller and a client machine to simulate a corporate network.
* **Implement Threat Monitoring:** Configure Splunk to collect and analyze security logs (telemetry) from Windows endpoints to detect malicious or unauthorized activity.
* **Develop a Detection Rule:** Create a Splunk alert to specifically identify and flag successful, unauthorized logins.
* **Automate Incident Response:** Utilize the Shuffle SOAR platform to build an automated playbook that responds to the Splunk alert by notifying a security analyst via Slack.
* **Enable Analyst Action:** Provide the security analyst with an interactive option within the Slack notification to either disable the compromised user account or dismiss the alert.

---

### Technologies

The following technologies are used to build and secure this environment:

* **Active Directory:** A Windows Server is promoted to a domain controller to manage network resources and user accounts.
* **Splunk:** A powerful SIEM (Security Information and Event Management) platform used for ingesting, parsing, and analyzing security logs.
* **Shuffle:** A SOAR (Security Orchestration, Automation, and Response) platform that acts as the automation engine, connecting Splunk and Slack.
* **Slack:** The communication platform used to notify the security analyst of detected threats.
* **Virtualization:** Virtual machines (VMs) are used to host the Windows Server (domain controller), a Windows client, and an Ubuntu server (for Splunk).

---

### Project Workflow

This project is broken down into three main phases:

1.  **Environment Setup & Configuration:** This phase involves the logical design of the network, setting up the virtual machines, and configuring Active Directory. A Windows client is then joined to the domain to simulate an end-user workstation.

2.  **Telemetry & Detection:** The Ubuntu server is configured to run Splunk, which is then set up to ingest security logs from the Windows endpoints. A detection rule is created within Splunk to look for a specific security event—an unauthorized successful login.

3.  **Automation & Response:** The final phase focuses on building the automated response. A Shuffle playbook is created to trigger when the Splunk alert is fired. This playbook integrates with Slack to send a notification to the security analyst, providing them with the details of the event and an interactive button to take action on the compromised user account.

---

A detailed breakdown of the steps and the specific configurations will be provided in a separate document.