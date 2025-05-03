## ICS344 Phase 1 – Setup and Compromise the Service

Group 07 – Second Semester 2024/2025

Group Members
 1. Shahad Almarhoon – 202158610
 2. Ghufran Alhulaymi – 202175090
 3. Jood Faqera – 202182590

⸻

## Objective

The goal of this phase is to simulate a security breach by setting up a vulnerable environment (Metasploitable3) and attacking it using Kali Linux. The focus is on compromising the SSH service using:
 1. Metasploit Framework
 2. A custom script (bash)

This demonstrates a real-world scenario of exploiting weak/default credentials.

⸻

## Environment Setup

Victim Machine: Metasploitable3
 1. Deployed using VirtualBox
 2. Logged in with default credentials: vagrant:vagrant
 3. IP address obtained using ifconfig: 192.168.56.101
 4. Network connectivity verified using ping

Attacker Machine: Kali Linux
 1. Installed and configured Metasploit Framework
 2. Verified access to target machine over the network

⸻

## Task 1.1 – Exploiting SSH with Metasploit
 • Target Service: SSH
 • Port: 22
 • Tool: Metasploit

Steps
 1. Launch Metasploit
 2. Load SSH login scanner module
 3. Set the following options:
 • RHOST: 192.168.56.101
 • USERNAME: vagrant
 • PASSWORD: vagrant
 4. Run the exploit command

Outcome
 1. SSH session established
 2. Verified access with whoami
 3. Confirmed system vulnerability due to default credentials

⸻

## Task 1.2 – Exploiting SSH with Custom Script
 • Tool: Bash Script with sshpass
 • Target IP: 192.168.56.101
 • Credentials Used: vagrant:vagrant

Steps
 1. Created ssh_attack.sh script
 2. Script attempted SSH logins using known credentials
 3. On success, printed confirmation and executed whoami

Outcome
 1. Successful login with default credentials
 2. Verified remote access
 3. Demonstrated basic automation of credential attacks

⸻

## Key Takeaways
 1. Default credentials pose serious security risks
 2. Metasploit is a powerful tool for automating exploitation
 3. Bash scripting can efficiently brute-force access
 4. Mitigation requires:
 5. Changing default passwords
 6. Enforcing strong credential policies
 7. Adding protections like rate-limiting or multi-factor authentication
