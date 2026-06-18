# Day-3 SSH Hardening

## Objective

Harden the SSH configuration by disabling root login, enforcing key-based authentication, validating the SSH configuration, and ensuring secure remote access.

---

## 1. Backup SSH Configuration

Created a backup of the original SSH configuration file before making changes.

### Command

```bash
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.backup
```

### Verification

```bash
ls -l /etc/ssh/sshd_config*
```

### Result

- Original SSH configuration preserved.
- Backup file created successfully.

### Screenshot

`01-ssh-config-backup.png`

---
<img width="613" height="65" alt="backup ssh config" src="https://github.com/user-attachments/assets/172ec3f6-044f-49b6-83a8-6de40e2c87c0" />


## 2. Modify SSH Configuration

Edited the SSH daemon configuration file to harden remote access.

### Command

```bash
sudo nano /etc/ssh/sshd_config
```

### Configuration Applied

```text
PermitRootLogin no
PubkeyAuthentication yes
PasswordAuthentication no
```

### Result

- Root login disabled.
- Public key authentication enabled.
- Password authentication disabled.

### Screenshot

`02-ssh-config-edited.png`

---
<img width="612" height="453" alt="open and change configs" src="https://github.com/user-attachments/assets/b920972c-05fe-4bae-8788-83d38a8dd27e" />


## 3. Verify Effective SSH Configuration

Verified that the SSH daemon is using the intended security settings.

### Command

```bash
sudo sshd -T | grep -E 'passwordauthentication|pubkeyauthentication|permitrootlogin'
```

### Expected Output

```text
permitrootlogin no
pubkeyauthentication yes
passwordauthentication no
```

### Result

- Effective SSH settings confirmed.
- Secure authentication policy verified.

### Screenshot

`03-verify-ssh-configuration.png`

---
<img width="846" height="123" alt="verify config" src="https://github.com/user-attachments/assets/f5c55805-e2bd-451e-8dc2-64b6d2fa26d5" />


## 4. Validate SSH Configuration Syntax

Checked the SSH configuration file for syntax errors before restarting the service.

### Command

```bash
sudo sshd -t
```

### Result

- No errors returned.
- SSH configuration syntax is valid.

### Screenshot

`04-sshd-syntax-check.png`

---
<img width="292" height="32" alt="check ssh config syntex" src="https://github.com/user-attachments/assets/e36a7ea7-a588-41a4-b200-357dbca56bdb" />


## 5. Restart and Verify SSH Service

Restarted the SSH service and verified that it is running correctly.

### Commands

```bash
sudo systemctl restart ssh
sudo systemctl status ssh --no-pager
```

### Result

```text
Active: active (running)
```

### Result

- SSH daemon restarted successfully.
- Secure Shell service is active and operational.

### Screenshot

`05-ssh-service-running.png`

---
<img width="733" height="368" alt="restart ssh services" src="https://github.com/user-attachments/assets/b2460da6-0eff-4e41-ae23-3a3a3dc89960" />


## 6. Verify Key-Based Authentication

Tested SSH access using the ED25519 private key.

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

- SSH connection established successfully.
- Authentication performed using the SSH key.
- Secure access verified.

### Screenshot

`06-key-based-authentication-success.png`

---
<img width="607" height="465" alt="Verify Key-Based Login Still Works" src="https://github.com/user-attachments/assets/ddc21e60-f7ca-4039-9ddf-ab97442f9423" />


## Technologies Used

- Ubuntu Server 26.04 LTS
- OpenSSH Server
- ED25519 SSH Keys
- Linux System Administration
- VMware Workstation

---

## Outcome

Successfully hardened the SSH service by disabling root login, enabling public key authentication, validating the configuration, restarting the SSH service, and verifying secure access using SSH keys.

---

## Status

✅ SSH Configuration Backup Created

✅ Root Login Disabled

✅ Public Key Authentication Enabled

✅ Password Authentication Disabled

✅ SSH Configuration Validated

✅ SSH Service Restarted Successfully

✅ Key-Based Authentication Verified

✅ Day 3 Completed
