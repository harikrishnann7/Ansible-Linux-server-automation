Ansible Linux Automation
==========================

Project Overview

Automate Linux server connectivity checks using Ansible on Ubuntu, including multiple SSH users on the same IP address with timestamped logging.

Features

- Single-user and multi-user SSH connectivity checks.
- Inventory management using "ansible_user".
- Parallel host checks using Ansible.
- Timestamped execution logs.
- SSH connectivity troubleshooting.

Technologies

- Ubuntu Linux
- Ansible
- OpenSSH
- Bash
- Git and GitHub

Inventory Example

[Ubuntu]
server1 ansible_host=192.0.2.10 ansible_user=ansible
server2 ansible_host=192.0.2.10 ansible_user=raju
server3 ansible_host=192.0.2.10 ansible_user=haju

Replace the example IP with your authorized target IP.

Execution

ansible -i inventory all -m ping

Timestamped Logging

ansible -i inventory all -m ping -o 2>&1 | while IFS= read -r line; do echo "$(date '+%Y-%m-%d %H:%M:%S') $line"; done | tee -a ansibleping.log

Prerequisites

- Ansible installed on the Ubuntu control node.
- SSH access and valid authentication for each user.
- Python available on managed hosts.

Learning Outcomes

- Ansible inventory and SSH authentication.
- Linux command-line automation.
- Multi-user connectivity validation.
- Timestamped log management.
- Git version control.

Security

Never commit passwords, private SSH keys, or sensitive production inventories and logs.
