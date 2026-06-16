# Day 1 - Ubuntu Server Deployment

## Objective

Deploy an Ubuntu Server virtual machine using VMware and verify basic connectivity.

## Environment

| Component | Value |
|------------|------------|
| Hypervisor | VMware Workstation |
| OS | Ubuntu Server 26.04 LTS |
| RAM | 2 GB |
| CPU | 2 vCPUs |
| Disk | 20 GB |
| Network | NAT |

<img width="751" height="717" alt="image" src="https://github.com/user-attachments/assets/2a9805d6-132e-4312-a6fc-548fc8aaf870" />

## Profile Configuration
<img width="1257" height="524" alt="ubserver name" src="https://github.com/user-attachments/assets/82a4a434-145c-41b8-be07-677525422d7f" />

## Ubuntu Server Home
<img width="1290" height="641" alt="image" src="https://github.com/user-attachments/assets/d2efa4e4-c303-447b-8ca6-3626f221fced" />


## Verification Commands

### Hostname

```bash
hostnamectl
```
<img width="475" height="294" alt="Hostnamectl ubtsvr" src="https://github.com/user-attachments/assets/7218e3f9-8849-4cc6-820a-93750bace889" />

### Current User

```bash
whoami
```
<img width="221" height="33" alt="Whoami ubtsvr" src="https://github.com/user-attachments/assets/a43751fd-e38d-4eec-ae2e-493a8339ed23" />

### Network Information

```bash
ip a
```
<img width="839" height="243" alt="(ip a) ubtsvr " src="https://github.com/user-attachments/assets/fea61815-df71-4462-92e0-721cb6e57b75" />

### SSH Service Status

```bash
sudo systemctl status ssh --no-pager
```
<img width="696" height="127" alt="Status ssh ubtsvr" src="https://github.com/user-attachments/assets/12e956a3-e15c-4a3d-928f-742179228f30" />

### Package Update

```bash
sudo apt upgrade -y
```
<img width="1116" height="128" alt="apt upgrade ubtsvr" src="https://github.com/user-attachments/assets/08d16a12-921e-4e4c-8f5b-da7b3bb798f9" />


## Result

- Ubuntu Server installed successfully
- Network connectivity verified
- OpenSSH Server installed
- Package repositories reachable
- System ready for SSH configuration

## IP Address

```text
192.168.189.130
```
