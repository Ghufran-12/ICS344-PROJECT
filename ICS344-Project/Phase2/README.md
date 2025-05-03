## ICS344 Phase 2 – SIEM Setup & Attack Monitoring

Group 07 – Second Semester 2024/2025

Group Members
 1. Shahad Almarhoon – 202158610
 2. Ghufran Alhulaymi – 202175090
 3. Jood Faqera – 202182590

⸻

## Objective

The goal of this phase is to deploy Splunk as a SIEM to monitor and analyze attack logs from the compromised Metasploitable3 machine (Phase 1). We will:
 1. Install and configure Splunk Enterprise (SIEM server).
 2. Set up Splunk Universal Forwarder on Metasploitable3 to send logs.
 3. Monitor SSH brute-force attacks and unauthorized access attempts.

⸻

## Environment Setup

SIEM Server: Kali Linux 
 1. Installed Splunk Enterprise (v9.3.2) via .deb package.
 2. Configured Splunk to run on startup (enable boot-start).
 3. Accessed the web interface at http://10.0.2.15:8000.

Victim Machine: Metasploitable3
 1. Installed Splunk Universal Forwarder
 2. Configured forwarding to SIEM
 3. Monitored /var/log/auth.log for SSH attacks add monitor /var/log/auth.log.

⸻

## TTask 2.1 – Splunk SIEM Configuration
 • Tool: Splunk Enterprise
 • Purpose: Centralized log collection & attack detection.

Steps
 1. Launched Splunk Web and loggedin.
 2. Created an index for storing authentication logs.
 3. Configured a real-time alert for failed SSH login attempts.
 4. Built a dashboard to visualize attack patterns.

Outcome
 1. Successful log ingestion from Metasploitable3.
 2. Verified access with whoamiDetected brute-force attempts from Phase 1 attacks.

⸻

## Task 2.2 – Attack Analysis & Reporting
 • Tool: Splunk Search Processing Language (SPL)
 • Purpose: Identify malicious activity in logs.

Steps
 1. Ran SPL query to filter failed SSH attempts
 2. Identified attacker IP
 3. Generated a report showing attack frequency and methods.

Outcome
 1. Confirmed exploitation attempts from Phase 1.
 2. Verified Splunk’s capability to detect credential-based attacks.

⸻

## Key Takeaways
 1. SIEMs like Splunk provide critical visibility into attacks.
 2. Log forwarding ensures centralized monitoring.
 3. Real-time alerts help in early attack detection.
 4. Mitigation strategies:
    • Enforce strong passwords and key-based SSH.
    • Implement fail2ban to block brute-force attempts.
    • Use Splunk dashboards for continuous monitoring.
