# Role: cpu_settings

This Ansible role is designed to set the CPU governor to a productive mode (e.g., `performance`) and ensure that the setting persists across reboots. The role supports multiple methods of applying and maintaining the CPU governor, including using `cpupower` (via systemd) and directly modifying the `sysfs` files.

## Requirements

- The system must have the `cpupower` tool installed.
- The system should be configured to use either `cpupower` or direct manipulation of the `sysfs` CPU frequency settings.

## Variables

- `cpu_governor`: The desired CPU governor to set. Default is `performance`. You can set this to other values like `powersave`, `ondemand`, etc.

### Example of Inventory File:

```yaml
all:
  hosts:
    server1:
      cpu_governor: performance  # Set this to 'performance' or another desired governor