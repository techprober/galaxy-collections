# Ansible Collection Role: techprober.minio.setup

An Ansible Role to upgrade minio clientfor any linux distributions

## Requirements

You will need to run the role [techprober.minio.setup](https://github.com/techprober/galaxy-collections/tree/master/collections/minio/roles/setup) before running this role.

## Dependencies

None.

## Example Playbook

```yaml
- name: Keep minio client up-to-date
  hosts: all
  become: yes

  roles:
    - role: techprober.minio.upgrade
```

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Kevin Yu](https://github.com/yqlbu)
