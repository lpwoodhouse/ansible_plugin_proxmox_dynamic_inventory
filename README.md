# Ansible Play: proxmox_host_inventory

## Purpose

This play is for creating a dynamic inventory in AWX from a ProxmoxVE host

## Requirements

community.general
ansible.utils

## Default Playbook Variables

Default playbook variables are listed below:
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

MIT

## Author Information

This role was created in 2022 by [Lee Woodhouse](https://www.leewoodhouse.com/)
