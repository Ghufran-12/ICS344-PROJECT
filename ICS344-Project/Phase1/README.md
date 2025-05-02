## ICS344 Phase 1 – Setup and Compromise the Service

Group 07 – Second Semester 2024/2025

Group Members
 • Shahad Almarhoon – 202158610
 • Ghufran Alhulaymi – 202175090
 • Jood Faqera – 202182590

⸻

## Objective

The goal of this phase is to simulate a security breach by setting up a vulnerable environment (Metasploitable3) and attacking it using Kali Linux. The focus is on compromising the SSH service using:
 • Metasploit Framework
 • A custom script (bash)

This demonstrates a real-world scenario of exploiting weak/default credentials.

⸻

## Environment Setup

Victim Machine: Metasploitable3
 • Deployed using VirtualBox
 • Logged in with default credentials: vagrant:vagrant
 • IP address obtained using ifconfig: 192.168.56.101
 • Network connectivity verified using ping

Attacker Machine: Kali Linux
 • Installed and configured Metasploit Framework
 • Verified access to target machine over the network

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
 • SSH session established
 • Verified access with whoami
 • Confirmed system vulnerability due to default credentials

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
 • Successful login with default credentials
 • Verified remote access
 • Demonstrated basic automation of credential attacks

⸻

## Key Takeaways
 • Default credentials pose serious security risks
 • Metasploit is a powerful tool for automating exploitation
 • Bash scripting can efficiently brute-force access
 • Mitigation requires:
 • Changing default passwords
 • Enforcing strong credential policies
 • Adding protections like rate-limiting or multi-factor authentication
