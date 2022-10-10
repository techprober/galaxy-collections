# Ansible Collection Role: techprober.apt.set_sources

An Ansible Role to update apt sources for linux (ubuntu-distributions)

## Requirements

None.

## Dependencies

None.

## Role Variables

Notes: Available variables are listed below, along with default values (see `defaults/main.yml`):

The default url for `primary_source`

```
primary_source_uri: "https://mirrors.ustc.edu.cn/ubuntu/"
```

The default url for `security_source_uri`

```
security_source_uri: "https://mirrors.ustc.edu.cn/ubuntu/"
```

The release of `ubuntu` branch

```
release: "jammy"
```

## Example Playbook

```yaml
---
- hosts: all
  become: true

  roles:
    - role: techprober.apt.set_source
      vars:
        primary_source_uri: "https://mirrors.ustc.edu.cn/ubuntu/"
        security_source_uri: "https://mirrors.ustc.edu.cn/ubuntu/"
        release: "jammy"
```

## TODOs

- [ ] Add support for `debian` distributions

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Kevin Yu](https://github.com/yqlbu)
