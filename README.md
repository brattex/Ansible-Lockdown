# HPC Ecosystems Project
## Ansible Lockdown Scripts

*BrYan inspired to be living in convenience*

***

# How to run

1. Ansible installed
1. git clone this repo
1. cd Ansible-Lockdown
1. `ansible-playbook fail2ban_setup.yml`

***

## Pre-requisites
### Git
`sudo dnf install git -y`

### Ansible
`sudo dnf install -y epel-release`
`sudo dnf install -y ansible`

## Clone the repo

1. Create a local `/opt/ansible/` (or wherever)

`sudo mkdir -p /opt/ansible`

`sudo chown -R $USER:$USER /opt/ansible`

1. Clone repo to `/opt/ansible/`

`cd /opt/ansible`

`git clone git@gitlab.com:csir-nicis/chpc/hpc-ecosystems/infrastructure/ansible-lockdown.git`

OR

`git clone https://github.com/brattex/Ansible-Lockdown.git`

## Run the playbook

1. `sudo ansible-playbook fail2ban_setup.yml`

## verify

- `watch 'sudo fail2ban-client status sshd'`

## verify without SSH Key

`ssh -o PreferredAuthentications=password -o PubkeyAuthentication=no rocky@154.114.52.57`

```
rocky@154.114.52.57: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
```


***

20260418 updates:

# Ansible Lockdown  
Modular Security Hardening for Rocky Linux 9

This repository provides a modular, role‑based security baseline for Rocky Linux 9 systems.  
It currently includes two core hardening roles:

- **fail2ban** — protects SSH from brute‑force attacks  
- **ssh_harden** — enforces secure SSH daemon configuration (e.g., disable root login)

The project follows the recommended Ansible best‑practice layout and is designed to expand into a full security baseline over time.

---

## 📁 Repository Structure

ansible-lockdown/
├── ansible.cfg
├── inventories/
│   └── localhost/
│       └── hosts
├── playbooks/
│   ├── fail2ban.yml
│   ├── ssh_harden.yml
│   └── lockdown.yml
└── roles/
    ├── fail2ban/
    └── ssh_harden/


---

## 🚀 Usage

### Run Fail2ban hardening

```bash
ansible-playbook playbooks/fail2ban.yml -i inventories/localhost/hosts


Run SSH hardening
ansible-playbook playbooks/ssh_harden.yml -i inventories/localhost/hosts


Run full lockdown baseline (all the roles)
ansible-playbook playbooks/lockdown.yml -i inventories/localhost/hosts


## Role Overview

- `fail2ban` installs & configures Fail2ban
- `ssh_harden` applies hardened SSH configurations
  - Disable root SSH login



