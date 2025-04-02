# Programmatic Remediation in Linux

![Introduction_Vulnerability Management Lab Overview](https://github.com/user-attachments/assets/395f93a3-db26-46b4-b8b3-de1d8514e576)

## Overview
This project focuses on **programmatic remediation of security vulnerabilities** in a **Linux Server (Ubuntu 22.04)** virtual machine. Using **Microsoft Azure** and **Tenable Vulnerability Management**, we provisioned a VM, performed authenticated vulnerability scans using the **DISA STIG template**, and automated the remediation process through scripting. This simulates real-world cybersecurity operations where analysts remediate vulnerabilities in enterprise environments.

## Tools & Technologies
- **Microsoft Azure** (Virtual Machine Provisioning)
- **Tenable Vulnerability Management** (Authenticated Scanning)
- **Bash Scripts** (Automated Remediation)

## Objectives
- Deploy a **Linux Server (Ubuntu 22.04) VM** in **Microsoft Azure**.
- Run an **authenticated vulnerability scan** using **Tenable** with the **DISA STIG template**.
- Simulate vulnerabilities by manually introducing security misconfigurations.
- Remediate vulnerabilities **programmatically** using **Bash scripts**.
- Re-run scans to verify remediation success.

---

## Project Breakdown 

### Step 1: Provision a Linux Server (Ubuntu 22.04)
1. Deploy a new **Virtual Machine (VM)** in **Microsoft Azure**.
2. Configure SSH access and authentication settings.
3. Ensure **Tenable** has proper credentials to perform an authenticated scan.

---

### Step 2: Perform an Authenticated Scan in Tenable
1. **Create an Authenticated Scan** using the **Linux DISA STIG** template.
2. Scan the Azure VM to identify **critical** and **high-risk** vulnerabilities.

#### What is DISA STIG?
The **Defense Information Systems Agency (DISA) Security Technical Implementation Guide (STIG)** provides security configuration guidelines to **harden IT systems** and enforce compliance, mainly used by the **Department of Defense (DoD)**.

![Screenshot 2025-03-28 005022](https://github.com/user-attachments/assets/ff5880f7-944a-4142-82c3-5d51626098c8)

---

### Step 3: Simulate Vulnerabilities
To **mimic real-world security threats**, we manually introduced the following vulnerabilities:

1. **Installed Telnet** *(Insecure Protocol)*
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Install%20and%20Start%20Telnet)

2. **Set Root Account Password as "root"** *(Weak Password Policy)*
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Enable%20Password%20as%20Root)

3. **Installed an Outdated OpenSSL Version** *(Vulnerable Cryptographic Library)*
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/SCRIPT%3A%20Install%20Vulnerable%20OpenSSL)

After introducing these vulnerabilities, we performed **another scan** to capture the **pre-remediation** state.

![Initial Scan Linux](https://github.com/user-attachments/assets/928551b2-6af9-4c5a-9f8b-1dadfab06499)

---

## Remediation Process

### Step 4: Automate Vulnerability Remediation
To **programmatically remediate vulnerabilities**, we wrote **Bash scripts** that automate the removal of insecure configurations.

1. **Remove Telnet (Insecure Protocol)**
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/remediation-Telnet-Remove.sh)

2. **Enforce Secure Root Password Policy**
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/remediation-root-password.sh)

3. **Upgrade OpenSSL to a Secure Version**
   - [View Script](https://github.com/cybererik/Programmatic-Remediation-in-Linux/blob/main/remediation-openssl-update.sh)

Each script ensures that vulnerabilities are mitigated **without manual intervention**.

---

### Step 5: Verification & Post-Remediation Scan
Once remediation was completed, we **re-ran the authenticated scan** to verify that the **critical and high vulnerabilities** were successfully mitigated.

**Expected Outcome:**

✔️ **Telnet removed**  

✔️ **Strong password policy enforced**  

✔️ **OpenSSL updated to a secure version**  

![Second Scan Linux](https://github.com/user-attachments/assets/859d6d97-92c3-4629-8724-843aa1e61fdb)

---

## Conclusion
This project demonstrated how **programmatic remediation** can be leveraged in enterprise cybersecurity to **automate vulnerability management**. By combining **Tenable’s scanning capabilities** with **Bash scripting**, we created a **scalable** and **efficient** approach to security hardening.

### Future Enhancements
- Integrate **Ansible/Puppet** for large-scale remediation.
- Automate scans and remediation via **CI/CD pipelines**.
- Expand remediation scripts to **cover additional vulnerabilities**.

---

## References
- [DISA STIGs](https://public.cyber.mil/stigs/)
- [Tenable Vulnerability Management](https://www.tenable.com/)
- [Microsoft Azure Virtual Machines](https://azure.microsoft.com/en-us/products/virtual-machines/)
