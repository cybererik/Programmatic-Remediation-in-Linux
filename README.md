# Programmatic Remediation in Linux

![Introduction_Vulnerability Management Lab Overview](https://github.com/user-attachments/assets/395f93a3-db26-46b4-b8b3-de1d8514e576)

## Overview
This project focuses on programmatic remediation of security vulnerabilities in a Linux Server (Ubuntu 22.04) virtual machine. By leveraging tools like Microsoft Azure and Tenable, we provisioned a VM, performed authenticated vulnerability scans using the DISA STIG template, and automated the remediation process using scripts. This project simulates the actions a cybersecurity analyst would take to resolve vulnerabilities in an enterprise environment.

## Tools & Technologies
- **Microsoft Azure** (Virtual Machine)
- **Tenable Vulnerability Management Platform** (Authenticated Scans)
- **Scripts** (Automated Remediation Scripts)

## Objective(s)
- Provision a Linux Server (Ubuntu 22.04) VM on Microsoft Azure.
- Run an authenticated vulnerability scan using Tenable Enterprise with the DISA STIG template.
- Simulate vulnerability creation (e.g., insecure protocols, insecure configurations).
- Remediate vulnerabilities programmatically using scripts.
- Re-run authenticated scans to verify remediation success.

## Project Overview 

### Step 1: Provision a Linux Server (Ubuntu 22.04)
1. Create a new Virtual Machine (VM) on **Microsoft Azure** with Linux Server (Ubuntu 22.04) as the OS.
---
### Step 2: Create an Authenticated Scan in Tenable
1. Create an **Authenticated Scan** using the **Linux DISA STIG** template to scan the VM for vulnerabilities.

#### What is DISA STIG?
**DISA STIG (Defense Information Systems Agency Security Technical Implementation Guide)** provides configuration guidelines to harden IT systems and enforce cybersecurity compliance, mainly for the Department of Defense (DoD).

![Screenshot 2025-03-28 005022](https://github.com/user-attachments/assets/ff5880f7-944a-4142-82c3-5d51626098c8)
----
### Step 3: Manually Introduce Vulnerabilities
To simulate common vulnerabilities, we manually introduced several issues:
1. **Installed Telnet** (Insecure protocol)
   - [Script Link](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Install%20and%20Start%20Telnet)

2. **Set Root Account Password as Root** (Insecure configuration)
   - [Script Link](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Enable%20Password%20as%20Root)

3. **Default OpenSSL** (xxxxx)
 - [Script Link](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Enable%20Password%20as%20Root)

----
### Step 4: Run Authenticated Scan
Run a **Authenticated Scan** on the **Azure VM** using Tenable to capture the state of the vulnerabilities. This provides a baseline before remediation.

![Inistal scan Linux](https://github.com/user-attachments/assets/928551b2-6af9-4c5a-9f8b-1dadfab06499)


-----
## Remediation Step

### Step 5: Created Scripts for Programmatic Remediation
To simulate real-world remediation in large environments, I wrote scripts to automate vulnerability remediation. The goal is to remove bad configurations automatically, without manual intervention, while testing the scripts in a sandbox environment first.

1. **Remediate Telnet:**: 
   - [Script Link](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-Telnet-Remove.sh)

2. **Remediate Default Root Password:**: 
   - [Script Link](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-root-password.sh)

3. **Remediate OpenSSL:**: 
   - [Script Link](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-openssl-3.0.5-install.sh)


## Testing & Verification
After running the scan post-remediation, compare the results with the previous scan to evaluate the effectiveness of the automated remediation. Successful remediation should show a reduction in the number of critical vulnerabilities, and the system should now meet security compliance standards.

![SECOND SCAN Screenshot 2025-04-01 223115](https://github.com/user-attachments/assets/859d6d97-92c3-4629-8724-843aa1e61fdb)


## Conclusion
In this project, we simulated a real-world remediation process by leveraging tools like Tenable Enterprise and PowerShell. By automating the remediation of vulnerabilities, we demonstrated the importance of efficient, scalable solutions for managing system security. Future improvements could include extending the scripts to handle more vulnerabilities or integrating this process into a Continuous Integration/Continuous Deployment (CI/CD) pipeline for automated security compliance checks.

## References
- [DISA STIGs](https://public.cyber.mil/stigs/)
