# Day 2 - User Management & SSH Key Authentication

## Objective

Create an administrative user, configure SSH key-based authentication, and verify secure SSH access on the Ubuntu Server.

---

## 1. Administrative User Creation

Created a dedicated administrative user for server management.

### Command

```bash
sudo adduser ubtadmin
```

### Result

- New user account created successfully.
- Home directory generated automatically.
- User information configured during setup.

### Screenshot

`01-add-user.png`

---
<img width="557" height="275" alt="add User" src="https://github.com/user-attachments/assets/46fbbf8d-c292-4a18-b6fc-cb6b0b0e91e4" />


## 2. Assigning Sudo Privileges

Added the new user to the sudo group for administrative access.

### Command

```bash
sudo usermod -aG sudo ubtadmin
```

### Verification

```bash
groups ubtadmin
```

### Output

```text
ubtadmin : ubtadmin sudo users
```

### Result

- Administrative privileges successfully assigned.
- User can execute privileged commands using sudo.

### Screenshot

`02-group-user.png`

---
<img width="429" height="49" alt="Group user" src="https://github.com/user-attachments/assets/a04cfa98-f104-4121-a8fe-6cda85d9f18d" />


## 3. User Verification

Verified that the newly created user exists in the system.

### Command

```bash
cat /etc/passwd | grep ubtadmin
```

### Result

- User account successfully located in the system database.
- Home directory and login shell verified.

### Screenshot

`03-check-user-exist.png`

---
<img width="669" height="49" alt="check user exist" src="https://github.com/user-attachments/assets/dba4ba4b-d215-425a-841e-9059ff651c43" />


## 4. SSH Key Pair Generation

Generated an ED25519 SSH key pair for secure authentication.

### Command

```bash
ssh-keygen -t ed25519
```

### Files Generated

```text
sshkey
sshkey.pub
```

### Result

- Private key created successfully.
- Public key generated successfully.

### Screenshot

`04-create-ssh-key.png`

---
<img width="608" height="338" alt="Create SSH key" src="https://github.com/user-attachments/assets/7abf5595-4f4b-453c-aaa2-b6a7e600bd09" />


## 5. Public Key Verification

Verified the generated public key.

### Command

```bash
cat sshkey.pub
```

### Result

- Public key displayed successfully.
- Key ready for authorized_keys configuration.

### Screenshot

`05-verify-ssh-key.png`

---
<img width="795" height="59" alt="verify SSHkey" src="https://github.com/user-attachments/assets/4ebd08bb-b29b-4a46-9d7b-a947687ae7bb" />


## 6. SSH Key Configuration

Configured SSH key authentication.

### Commands

```bash
mkdir -p ~/.ssh
chmod 700 ~/.ssh

cat sshkey.pub >> ~/.ssh/authorized_keys

chmod 600 ~/.ssh/authorized_keys
```

### Verification

```bash
ls -la ~/.ssh
```

### Result

- SSH directory created.
- authorized_keys configured successfully.
- Correct file permissions applied.

### Screenshot

`06-authorized-and-verify-ssh-keys.png`

---
<img width="715" height="213" alt="authorized and verify SSH keys" src="https://github.com/user-attachments/assets/b8f150ad-da9f-4143-a6ba-49ee7d844117" />


## 7. SSH Authentication Testing

Tested SSH login using the generated key.

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
- Public key authentication verified.
- User identity confirmed.

### Screenshot

`07-test-ssh-authentication.png`

---
<img width="641" height="563" alt="test SSH authentication" src="https://github.com/user-attachments/assets/a93edc35-c39d-4bed-8427-653d1c3cd83c" />


## 8. SSH Service Verification

Verified that the OpenSSH service is active and running.

### Command

```bash
sudo systemctl status ssh --no-pager
```

### Result

```text
Active: active (running)
```

### Additional Verification

```text
Accepted publickey for ubtsvr
```

This confirms successful SSH key authentication.

### Screenshot

`08-verify-ssh-services.png`

---
<img width="834" height="383" alt="verify SSH Services" src="https://github.com/user-attachments/assets/ee39b241-d1c0-4eb9-9589-bcbad9a26bab" />


## Technologies Used

- Ubuntu Server 26.04 LTS
- OpenSSH Server
- ED25519 SSH Keys
- Linux User Management
- VMware Workstation

---

## Outcome

Successfully created an administrative user, assigned sudo privileges, generated SSH keys, configured key-based authentication, verified SSH access, and confirmed the OpenSSH service is running correctly.

---

## Status

✅ Administrative User Created

✅ Sudo Privileges Assigned

✅ User Verified

✅ SSH Key Generated

✅ Public Key Verified

✅ authorized_keys Configured

✅ SSH Authentication Tested

✅ SSH Service Verified

✅ Day 2 Completed
