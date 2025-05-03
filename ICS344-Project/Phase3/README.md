## ICS344 Phase 3 – Secure the Vulnerable Service

Group 07 – Second Semester 2024/2025

Group Members
 1. Shahad Almarhoon – 202158610
 2. Ghufran Alhulaymi – 202175090
 3. Jood Faqera – 202182590

⸻

## Objective

The goal of this phase is to implement and verify a defense mechanism to secure the vulnerable ProFTPD service previously exploited. The solution involves configuration hardening, then rerunning the original attack to validate the fix.

⸻

## Recap of the Attack (from Phase 1)

Service: ProFTPD  
Attack Method:
 - Used SITE CPFR and SITE CPTO commands to upload a PHP reverse shell (exploit.php) to the web directory
 - Reverse shell triggered remote access to the attacker's machine

Tools Used:
 - Custom Bash Script
 - Metasploit

⸻

## Task 3.1 – Implementing the Defense

Defense Method: Configuration Hardening

Steps
 1. Located config file: /opt/proftpd/etc/proftpd.conf
 2. Disabled dangerous commands: SITE CPFR, SITE CPTO
 3. Limited FTP access to localhost only
 4. Disabled anonymous write access
 5. Restarted the service:
    ```bash
    sudo /etc/init.d/proftpd restart
    ```

⸻

## Task 3.2 – Verifying

Verification Method:
 - Re-executed custom Phase 1 attack script
 - Retried Metasploit-based attack

Outcome
 1. Upload attempts failed – exploit.php not transferred
 2. No shell session established
 3. Netcat listener received no connection

⸻

## Results Comparison

**Before Defense (Phase 1)**:
 - FTP commands successfully uploaded reverse shell
 - Remote access gained by attacker

**After Defense (Phase 3)**:
 - FTP commands blocked
 - Upload blocked, no shell created

⸻

## Key Takeaways
 1. Disabling unused or risky FTP commands mitigates specific attack vectors
 2. Configuration changes can effectively stop exploitation
 3. Testing and validation are essential after applying security changes
 4. Properly hardened services reduce exposure without requiring external tools
