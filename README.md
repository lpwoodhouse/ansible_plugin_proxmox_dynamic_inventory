# Ansible Plugin: proxmox_dynamic_inventory
![GitHub last commit](https://img.shields.io/github/last-commit/lpwoodhouse/ansible_plugin_proxmox_dynamic_inventory)
![GitHub repo file count](https://img.shields.io/github/directory-file-count/lpwoodhouse/ansible_plugin_proxmox_dynamic_inventory)
![GitHub top language](https://img.shields.io/github/languages/top/lpwoodhouse/ansible_plugin_proxmox_dynamic_inventory)

## Purpose

This play is for creating a dynamic inventory in AWX from a ProxmoxVE host

## Requirements

community.general<br>
ansible.utils

## Default Playbook Variables

Default plugin variables are listed below:
```shell
user: <root@pam>
password: <password>
url: <host_url> #eg https://192.168.0.1:8006
```
## Dependencies

None

## Example Playbook
```yaml
plugin: community.general.proxmox
user: root@pam
password: password
url: https://192.168.0.1:8006
validate_certs: false
#want_facts: true
want_proxmox_nodes_ansible_host: false
compose:
  ansible_host: proxmox_ipconfig0.ip | default(proxmox_net0.ip) | ipaddr('address')
```

## License

[![GitHub](https://img.shields.io/github/license/lpwoodhouse/ansible_plugin_proxmox_dynamic_inventory)](LICENSE)

## Author Information

This repository was created in 2022 by [Lee Woodhouse](https://www.leewoodhouse.com/)
