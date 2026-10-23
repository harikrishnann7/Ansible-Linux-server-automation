Ansible Ubuntu Server Connectivity Check
=========================================
Project Overview
Automate SSH-based connectivity checks across multiple Ubuntu servers using Ansible from a central Ubuntu control node.

Objectives:
Check connectivity to 100+ servers in a single execution.
Use SSH key-based authentication.
Run Ansible's ping module against inventory hosts.
Execute checks concurrently using Ansible forks.
Save command output to timestamped log files.
Identify unreachable hosts for further troubleshooting.

Technologies:
Ubuntu Linux
Ansible
OpenSSH
Bash scripting
Git and GitHub

Prerequisites:
Ubuntu control node with Ansible installed.
Remote Ubuntu servers accessible over SSH for One time set-up.
Ansible user configured with appropriate permissions for NOPASSWD.
SSH public key installed on the remote servers.
Python available on managed hosts.

Usage :
Configure your inventory using "inventory" as a reference.
Create a local inventory file with your authorized server addresses.
Verify SSH authentication.

Run:
ansible -i inventory all -m ping -u ansible | tee -a ansible_ping.log

Alternatively:
ansible -i inventory all -m ping -u ansible

Expected Output:
Successful hosts return SUCCESS and pong. 
Unreachable or misconfigured hosts return an error that can be investigated.

Logging
The script saves Ansible output to a timestamped file in the local logs/ directory. Log files are excluded from version control.

Security
Never commit private SSH keys, passwords, production inventories, or sensitive logs.

Learning Outcomes
Ansible inventory management
SSH authentication
Parallel server connectivity checks
Linux shell scripting
Basic automation logging
Git version control
