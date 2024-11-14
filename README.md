# Ansible Role: Server Preparation

This Ansible project prepares servers for operation by encrypting secondary disks, configuring CPU performance, renaming network interfaces, and displaying system information.

## Requirements
- Ansible 2.9+
- SSH access to target servers

## Inventory Configuration
Set the desired partition to encrypt and other configurations in `group_vars/all.yml` or override in the `inventory/hosts.yml` file.

## Usage

Run the playbook as follows:

```bash
ansible-playbook -i inventory/hosts.yml prepare_host.yml