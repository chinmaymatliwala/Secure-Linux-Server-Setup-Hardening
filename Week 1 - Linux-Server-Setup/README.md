# Week 1 - Linux Server Deployment and Secure Configuration

## Objective

Deploy and secure an Ubuntu Server environment by configuring SSH access and implementing firewall protection.

---

# Tasks Completed

## Day 1 – Linux Server Deployment

### Activities

* Installed Ubuntu Server 26.04 LTS on VMware Workstation.
* Configured network connectivity.
* Installed OpenSSH Server.
* Verified internet connectivity and system configuration.

### Outcome

* Ubuntu Server deployed successfully.
* SSH service installed and operational.

---

## Day 2 – User Management and SSH Key Authentication

### Activities

* Created an administrative user (`ubtadmin`).
* Granted sudo privileges.
* Generated ED25519 SSH key pair.
* Configured `authorized_keys`.
* Tested SSH key-based login.

### Outcome

* Administrative user created successfully.
* Secure SSH key authentication implemented.

---

## Day 3 – SSH Hardening

### Activities

* Backed up SSH configuration.
* Disabled root login.
* Enabled public key authentication.
* Disabled password authentication.
* Restarted and verified SSH service.
* Tested SSH access using key authentication.

### Outcome

* SSH service hardened successfully.
* Secure remote access enforced.

---

## Day 4 – UFW Firewall Configuration

### Activities

* Verified UFW installation.
* Allowed OpenSSH traffic.
* Enabled UFW firewall.
* Verified firewall rules.
* Tested SSH connectivity after enabling firewall.

### Outcome

* Firewall configured successfully.
* Secure SSH access maintained.

---

## Day 5 – System Audit and Verification

### Activities

* Verified system information.
* Verified user configuration.
* Verified SSH service status.
* Verified firewall status.
* Checked open ports.
* Checked disk usage and memory usage.
* Verified internet connectivity.

### Outcome

* All server components functioning correctly.
* System configuration validated successfully.

---

# Tools and Technologies

* Ubuntu Server 26.04 LTS
* VMware Workstation
* OpenSSH Server
* UFW Firewall
* Linux User Management
* ED25519 SSH Keys
* Linux Networking Utilities

---

# Folder Structure

```text
week-1-linux-server-setup/ 
│
├── Day-1 Server-Deployment.md
│
├── Day-2 User Management & SSH Key Authentication.md
│
├── Day-3 ssh-hardening.md
│
├── Day-4 Firewall-Configuration.md
│
├── Day-5 System Audit and Verification.md
│
└── README.md
```

---

# Skills Gained

* Linux Server Deployment
* Linux User Management
* SSH Configuration and Hardening
* SSH Key-Based Authentication
* Firewall Configuration with UFW
* System Monitoring and Verification
* Basic Linux Administration

---

# Outcome

Successfully deployed and secured an Ubuntu Server environment by implementing secure SSH access and firewall protection. All Week 1 objectives were completed successfully.

---

## Status

✅ Ubuntu Server Deployed

✅ Administrative User Configured

✅ SSH Key Authentication Implemented

✅ SSH Hardening Completed

✅ UFW Firewall Configured

✅ System Audit Performed

✅ Week 1 Completed
