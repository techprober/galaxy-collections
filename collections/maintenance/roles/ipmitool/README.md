# Ansible Collection Role: techprober.maintenance.ipmitool

An Ansible Role to control remote server using ipmitool

## References

https://github.com/ipmitool/ipmitool

## Requirements

None.

## Dependencies

None.

## Role Variables

Define action to perform

```yaml
action: "power_control"
```

Define power state

```yaml
power_state: "on" # ["on", "off"]
```

Remote server host ip

```yaml
remote_server_ip: ""
```

IPMI admin password

```yaml
admin_password: ""
```

Whether to confirm action status

```yaml
check_status: true # default is set to true
```

## Example Playbook

```yaml
---
- name: Update power state on remote server
  hosts: localhost

  roles:
    - role: techprober.maintenance.ipmitool
      vars:
        - action: "power_control"
        - power_state: "on"
        - remote_server_ip: "10.178.0.19"
        - admin_password: !vault |
            $ANSIBLE_VAULT;1.1;AES256
            62363138343932376363383532313062373135356365313839353530613037646465623262353161
            3964366263333539383465346239316438383337376639620a393834336439353430316230386566
            35353266653465353264393838363764613565336461376562393864356431303538623531333533
            6230636131303936350a353634646435363332643039303236616437626530633763633766376330
            3135
        - check_status: true
```

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Kevin Yu](https://github.com/yqlbu)
