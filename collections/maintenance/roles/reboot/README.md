# Ansible Collection Role: techprober.maintenance.reboot

An Ansible Role to do something

## References

https://docs.ansible.com/ansible/latest/collections/ansible/builtin/reboot_module.html

## Requirements

None.

## Dependencies

None.

## Role Variables

Maximum seconds to wait for machine to reboot and respond to a test command, default is `300`

```yaml
reboot_timeout: 120
```

## Example Playbook

```yaml
# reboot-remote-servers.yml
---
- name: Reboot remote servers
  hosts: all

  roles:
    - role: techprober.maintenance.reboot
      vars:
        - reboot_timeout: 300
```

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Kevin Yu](https://github.com/yqlbu)
