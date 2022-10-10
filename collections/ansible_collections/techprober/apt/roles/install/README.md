# Ansible Collection Role: techprober.apt.install

An Ansible Role to manage apt packages for linux (ubuntu-distributions)

## Requirements

None.

## Dependencies

None.

## Role Variables

Notes: Available variables are listed below, along with default values (see `defaults/main.yml`):

The list of `base_packages` to be install/update

```
base_packages: []
```

The list of `user_defined_packages` to be install/update

```
extra_packages: []
```

## Example Playbook

```yaml
- hosts: all
  become: true

  roles:
    - role: techprober.apt.install
      vars:
        base_packages:
          - linux-headers-generic
          - linux-generic
          - vim
          - tree
        extra_packages:
          - tmux
          - net-tools
          - iputils-ping
          - telnet
          - dnsutils
          - screen
          - neofetch
```

## TODOs

- [ ] Add support for `debian` distributions

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Kevin Yu](https://github.com/yqlbu)
