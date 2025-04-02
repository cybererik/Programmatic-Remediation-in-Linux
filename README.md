# Programmatic Remediation in Linux

![Introduction_Vulnerability Management Lab Overview](https://github.com/user-attachments/assets/395f93a3-db26-46b4-b8b3-de1d8514e576)

## Overview
This project focuses on programmatic remediation of security vulnerabilities in a Linux Server (Ubuntu 22.04) virtual machine (VM). By leveraging tools like Microsoft Azure and Tenable, we provisioned a VM, performed authenticated vulnerability scans using the DISA STIG template, and automated the remediation process using PowerShell scripts. This project simulates the actions a cybersecurity analyst would take to resolve vulnerabilities in an enterprise environment.

## Tools & Technologies
- **Microsoft Azure** (Virtual Machine Provisioning)
- **Tenable Vulnerability Management** (Authenticated Scans)
- **Bash Scripts** (Automated Remediation)

## Objectives
- Provision a Linux Server (Ubuntu 22.04) VM on Microsoft Azure.
- Run an authenticated vulnerability scan using Tenable with the DISA STIG template.
- Simulate vulnerability creation (e.g., insecure protocols, misconfigurations).
- Remediate vulnerabilities programmatically using bash scripts.
- Re-run authenticated scans to verify remediation success.

---

## Project Breakdown 

### Step 1: Provision a Linux Server (Ubuntu 22.04) VM
1. Create a new Virtual Machine (VM) on **Microsoft Azure** with Linux Server (Ubuntu 22.04) as the OS.
--------
### Step 2: Create an Authenticated Scan in Tenable
1. Create an **Authenticated Scan** using the **Linux 10 DISA STIG** template to scan the VM for vulnerabilities.

#### What is DISA STIG?
**DISA STIG (Defense Information Systems Agency Security Technical Implementation Guide)** provides configuration guidelines to harden IT systems and enforce cybersecurity compliance, mainly for the Department of Defense (DoD).

![Screenshot 2025-03-28 005022](https://github.com/user-attachments/assets/ff5880f7-944a-4142-82c3-5d51626098c8)

---------
### Step 3: Simulate Vulnerabilities
To simulate common vulnerabilities, we manually introduced the following vulnerabilities:

1. **Installed Telnet** *(Insecure Protocol)*
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Install%20and%20Start%20Telnet)

2. **Set Root Account Password as "root"** *(Weak Password Policy)*
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Enable%20Password%20as%20Root)

3. **Installed an Outdated OpenSSL Version** *(Vulnerable Cryptographic Library)*
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Install%20Vulnerable%20OpenSSL)
----------
### Step 4: Run Authenticated Scan
Run a **Authenticated Scan** on the **Azure VM** using Tenable to capture the state of the vulnerabilities. This provides a baseline before remediation.

![Initial Scan Linux](https://github.com/user-attachments/assets/928551b2-6af9-4c5a-9f8b-1dadfab06499)

--------
## Remediation Process

### Step 5: Automate Vulnerability Remediation
To simulate real-world remediation in large environments, I created bash scripts to automate vulnerability remediation. The goal is to remove bad configurations automatically, without manual intervention, while testing the scripts in a sandbox environment first.

1. **Remove Telnet (Insecure Protocol)**
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/remediation-Telnet-Remove.sh)

2. **Enforce Secure Root Password Policy**
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/remediation-root-password.sh)

3. **Upgrade OpenSSL to a Secure Version**
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/remediation-openssl-update.sh)
------
## Testing & Verification
After running the scan post-remediation, compare the results with the previous scan to evaluate the effectiveness of the automated remediation. Successful remediation should show a reduction in the number of critical vulnerabilities, and the system should now meet security compliance standards.

**Expected Outcome:**

✔️ **Telnet removed**  

✔️ **Strong password policy enforced**  

✔️ **OpenSSL updated to a secure version**  

![Second Scan Linux](https://github.com/user-attachments/assets/859d6d97-92c3-4629-8724-843aa1e61fdb)

## Conclusion
In this project, we simulated a real-world remediation process by leveraging tools like Tenable Enterprise and Scripts. By automating the remediation of vulnerabilities, we demonstrated the importance of efficient, scalable solutions for managing system security. Future improvements could include extending the scripts to handle more vulnerabilities or integrating this process into a Continuous Integration/Continuous Deployment (CI/CD) pipeline for automated security compliance checks.

## References
- [DISA STIGs](https://public.cyber.mil/stigs/)
