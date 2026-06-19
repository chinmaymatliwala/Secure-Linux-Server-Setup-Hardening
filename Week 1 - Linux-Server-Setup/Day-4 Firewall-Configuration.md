# Day 4 - UFW Firewall Configuration

## Objective

Configure and enable the Uncomplicated Firewall (UFW) to secure the Ubuntu Server while maintaining SSH connectivity.

---

## 1. Verify UFW Status

Checked the current status of the firewall before applying any rules.

### Command

```bash
sudo ufw status
```

### Output

```text
Status: inactive
```

### Result

- UFW is installed.
- Firewall is initially disabled.

### Screenshot

`01-ufw-status.png`

---
<img width="287" height="68" alt="1 ufw status" src="https://github.com/user-attachments/assets/91c295de-718f-467d-bc14-9e37ad3cfa7c" />


## 2. Allow SSH Access

Configured UFW to allow SSH traffic through port 22.

### Command

```bash
sudo ufw allow OpenSSH
```

### Verification

```bash
sudo ufw status numbered
```

### Result

- OpenSSH rule added successfully.
- IPv4 and IPv6 rules created automatically.

### Screenshot

`02-allow-ssh.png`

---
<img width="361" height="98" alt="2 allow SSH" src="https://github.com/user-attachments/assets/9a072524-dcbb-4c2a-910d-b00f0d4ff59a" />


## 3. Enable Firewall

Enabled UFW and verified its configuration.

### Commands

```bash
sudo ufw enable
```

```bash
sudo ufw status verbose
```

### Output

```text
Status: active
Default: deny (incoming), allow (outgoing)
```

### Result

- Firewall activated successfully.
- Incoming connections blocked by default.
- Outgoing connections allowed.
- SSH traffic permitted.

### Screenshot

`03-enable-firewall.png`

---
<img width="494" height="240" alt="3 enable firewall" src="https://github.com/user-attachments/assets/80899cbb-a063-425e-838d-1393bba66028" />


## 4. Verify SSH Connectivity

Verified that SSH key-based authentication continues to function after enabling the firewall.

### Command

```bash
ssh -i sshkey localhost
```

### Verification

```bash
whoami
hostname
```

### Result

- SSH access successful.
- Key-based authentication functioning correctly.
- Firewall rules do not interfere with SSH connectivity.

### Screenshot

`04-verify-ssh-access.png`

---
<img width="624" height="448" alt="4 verify SSH access" src="https://github.com/user-attachments/assets/0ccf83d8-ee7b-430c-9e3c-ae0fc2c77cfe" />


## 5. Verify Firewall Rules

Checked the active firewall rules.

### Command

```bash
sudo ufw status numbered
```

### Output

```text
[1] OpenSSH ALLOW IN Anywhere
[2] OpenSSH (v6) ALLOW IN Anywhere (v6)
```

### Result

- SSH access allowed for IPv4 and IPv6.
- Firewall configuration verified successfully.

### Screenshot

`05-verify-rules.png`

---
<img width="466" height="121" alt="5 Verify rules" src="https://github.com/user-attachments/assets/b0717fd5-e13c-42c8-af43-232fcfff90f4" />


## Technologies Used

- Ubuntu Server 26.04 LTS
- UFW (Uncomplicated Firewall)
- OpenSSH Server
- ED25519 SSH Keys
- VMware Workstation

---

## Outcome

Successfully configured and enabled the UFW firewall while preserving secure SSH access. Firewall rules were verified, ensuring the server accepts only authorized SSH traffic.

---

## Status

✅ UFW Status Verified

✅ OpenSSH Rule Added

✅ Firewall Enabled

✅ SSH Connectivity Verified

✅ Firewall Rules Verified

✅ Day 4 Completed
