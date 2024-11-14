# Role: rename_interface

## Description

This Ansible role renames a network interface permanently on a Linux system. It supports:
- `udev`

## Requirements

- Ansible facts should be enabled to gather interface information.

## Role Variables

- `old_interface_name`: The current name of the interface (default: `"enX0"`).
- `new_interface_name`: The new desired name for the interface (default: `"net0"`).

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: rename_interface
      vars:
        old_interface_name: "enX0"
        new_interface_name: "net0"