![Ansible Lint](https://github.com/johanneskastl/ansible-role-libvirt_modular_systemd_services/workflows/Ansible%20Lint/badge.svg)

# libvirt_modular_systemd_services

Active the modular libvirt services and sockets (and disable the monolithic
ones)

## Requirements

Libvirt needs to be installed on the machine, this role only takes care of
enabling the modular daemons and their sockets.

## Role Variables

- `enable_libvirt_xen_sockets` (Boolean): Whether the Libvirt xen sockets
  (`virtxend{,-ro,-admin}.socket`) should be enabled and started (default:
  `undefined`)
- `enable_libvirt_proxy_sockets` (Boolean): To allow connections from remote
  machines are to be allowed, the `virtproxyd.service` and the related sockets
  (`virtproxyd{,-ro,-admin}.socket`) need to be enabled. This can be done by
  setting this variable to `true` (default: `undefined`)
- `enable_libvirt_tls_proxy_socket` (Boolean): In addition to the proxy service
  and sockets, you can set this variable to `true` to also enable the
  `virtproxyd-tls.socket` (default: `undefined`)

## Dependencies

None

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: 'johanneskastl.libvirt_modular_systemd_services'
```

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
