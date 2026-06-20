# Day 5 - System Audit & Verification

## Objective

Perform a basic system audit and verify that all configurations implemented during Week 1 are functioning correctly.

---

## 1. Verify System Information

Collected system and hardware information.

### Command

```bash
hostnamectl
```

### Result

- Hostname verified as `ubserver`
- Ubuntu Server 26.04 LTS confirmed
- VMware virtual machine environment verified
- Kernel version identified

### Screenshot

`01-verify-system-info.png`

---
<img width="427" height="311" alt="1 verify system info" src="https://github.com/user-attachments/assets/c52b617c-2212-4d57-8176-0659fd568b70" />


## 2. Verify User Configuration

Confirmed that the administrative user exists.

### Command

```bash
cat /etc/passwd | grep ubtadmin
```

### Result

- User `ubtadmin` exists
- Home directory assigned successfully
- Login shell configured

### Screenshot

`02-verify-system-users.png`

---
<img width="667" height="48" alt="2 verify system users" src="https://github.com/user-attachments/assets/338b531d-40a1-4b4e-acbb-3ed6e13d000b" />


## 3. Verify SSH Service

Checked the OpenSSH server status.

### Command

```bash
sudo systemctl status ssh --no-pager
```

### Result

```text
Active: active (running)
```

- SSH service running normally
- Port 22 listening successfully
- SSH key authentication functioning properly

### Screenshot

`03-verify-ssh-service.png`

---
<img width="846" height="406" alt="3 verify SSH service" src="https://github.com/user-attachments/assets/87068195-0f95-4c91-90f6-e09e0f491b62" />


## 4. Verify Firewall Status

Checked the UFW firewall configuration.

### Command

```bash
sudo ufw status verbose
```

### Result

```text
Status: active
Default: deny (incoming), allow (outgoing)
```

- Firewall enabled successfully
- OpenSSH traffic allowed
- Incoming traffic protected

### Screenshot

`04-verify-firewall-status.png`

---
<img width="504" height="194" alt="4 verify firewall status" src="https://github.com/user-attachments/assets/a80490b9-c4ad-41a7-9fa7-ebf762c26b1d" />


## 5. Verify Open Ports

Checked active network ports and listening services.

### Command

```bash
ss -tulnp
```

### Result

- SSH service listening on port 22
- DNS resolver services active
- Network services functioning correctly

### Screenshot

`05-check-open-ports.png`

---
<img width="808" height="191" alt="5 check open ports" src="https://github.com/user-attachments/assets/db126d21-366b-4169-bba5-1881eafa10b1" />


## 6. Verify Disk Usage

Checked storage utilization.

### Command

```bash
df -h
```

### Result

- Root partition utilization approximately 27%
- Sufficient disk space available

### Screenshot

`06-verify-disk-usage.png`

---
<img width="641" height="191" alt="6 verify disk usage" src="https://github.com/user-attachments/assets/47f5e1df-4a24-4b21-a993-dea6ee6e011c" />


## 7. Verify Memory Usage

Examined memory and swap usage.

### Command

```bash
free -h
```

### Result

- Memory consumption within normal range
- Swap space available and unused

### Screenshot

`07-verify-memory-usage.png`

---
<img width="650" height="81" alt="7 verify memory usage" src="https://github.com/user-attachments/assets/c6c31c63-a997-41e0-a4b4-f07da023d2f9" />


## 8. Verify Internet Connectivity

Confirmed external network connectivity.

### Command

```bash
ping -c 4 google.com
```

### Result

- All packets transmitted successfully
- No packet loss observed
- Stable internet connectivity verified

### Screenshot

`08-verify-internet-connectivity.png`

---
<img width="727" height="175" alt="8 verify internet connectivity" src="https://github.com/user-attachments/assets/dfecd536-3d03-4e00-b520-a3eeeb561957" />


## Technologies Used

- Ubuntu Server 26.04 LTS
- OpenSSH Server
- UFW Firewall
- Linux Networking Utilities
- VMware Workstation

---

## Outcome

Successfully verified system information, user configuration, SSH service, firewall rules, open ports, storage, memory utilization, and internet connectivity. All Week 1 configurations are functioning correctly.

---

## Status

✅ System Information Verified

✅ User Configuration Verified

✅ SSH Service Verified

✅ Firewall Status Verified

✅ Open Ports Checked

✅ Disk Usage Verified

✅ Memory Usage Verified

✅ Internet Connectivity Verified

✅ Day 5 Completed
