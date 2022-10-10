# Ansible Collection Role: techprober.apt.update

An Ansible Role to keep apt packages up-to-date for linux (ubuntu-distributions)

## Requirements

None.

## Dependencies

None.

## Role Variables

Notes: Available variables are listed below, along with default values (see `defaults/main.yml`):

The list of `dist_upgrade` to be install/update

```
dist_upgrade: no
```

## Example Playbook

```yaml
- hosts: all
  become: true

  roles:
    - role: techprober.apt.update
      vars:
        dist_upgrade: yes
```

## TODOs

- [ ] Add support for `debian` distributions

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Kevin Yu](https://github.com/yqlbu)
