# Ansible Collection Role: techprober.minio.backup

An Ansible Role to use minio client to backup files or directories for any linux distributions

## Requirements

None.

## Dependencies

None.

## Prerequisites

You will need to place a `backup.sh` script either under `/root/` or the user's home directory `/home/<user>/`

Example:

```bash
#!/bin/bash

mc mirror --overwrite --remove /home/packer/awx/ minio/server-configurations/awx/
mc cp /home/packer/backup.sh minio/server-configurations/awx/
```

## Role Variables

The path of the backup script

```yaml
script_path: /home/packer/backup.sh
```

## Example Playbook

```yaml
- name: Backup Data to Minio
  hosts: all

  roles:
    - role: techprober.minio.backup
      vars:
        - script_path: /home/packer/backup.sh
```

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Kevin Yu](https://github.com/yqlbu)
