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

## Run the playbook

1. `ansible-playbook fail2ban_setup.yml`
