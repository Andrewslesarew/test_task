# Role: encrypt_disk

## Description

This Ansible role encrypts specified partitions using LUKS encryption. It supports:
- Encrypting a disk (defined by `partitions_to_encrypt`).

The role performs the encryption non-interactively by using a predefined passphrase.

## Requirements

- LUKS and cryptsetup must be available on the target system.
- installed community.crypto ansible collection

## Role Variables

- `partitions_to_encrypt`: Path to the partitions to encrypt.
- `encryption_passphrase`: Passphrase for LUKS encryption.

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: encrypt_disk
      vars:
        partitions_to_encrypt:
          - partition: "/dev/sdb1"
            mapper_name: "encrypted_second_disk"
            mount_point: "/mnt/encrypted_second"
          - partition: "/dev/sda2"
            mapper_name: "encrypted_adjacent_partition"
            mount_point: "/mnt/encrypted_adjacent"
        encryption_passphrase: "MyStrongPassphrase"