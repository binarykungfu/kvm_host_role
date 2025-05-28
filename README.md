# KVM Host Role for RHEL 9

This Ansible role automates the configuration of a RHEL 9 server as a KVM-based virtualization host for home lab or testing environments.

## Features

- Installs essential KVM and libvirt packages
- Enables and configures `libvirtd` and `cockpit` for web-based VM management
- Sets up a bridge network for external VM connectivity
- Adds the target user to `kvm` and `libvirt` groups
- Enables and starts the default libvirt network

## Default Variables

```yaml
kvm_user: "{{ ansible_user }}"
bridge_name: br0
bridge_interface: enp1s0
```

> Customize the `bridge_interface` to match your physical NIC.

## Usage

```yaml
- hosts: kvm_hosts
  become: true
  roles:
    - kvm_host
```

## Requirements

- RHEL 9 or compatible (Rocky/AlmaLinux)
- NetworkManager enabled
- Ansible 2.10+

## License

MIT

## Author

[binarykungfu](https://gitlab.com/your-gitlab-username)
