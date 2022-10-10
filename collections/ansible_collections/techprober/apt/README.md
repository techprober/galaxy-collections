# TechProber Apt Collection

The `techprober-apt-collection` includes a variety of Ansible content to help automate the management of package managements for servers that are based on the `debian` system. This collection is maintained by the techprober core team.

## Ansible version compatibility

Tested with the Ansible Core `2.8`, `2.12`, and `2.13` releases, and the current development version of Ansible.

## Install this collection

You can install the `techprober.apt` collection with the Ansible Galaxy CLI:

```bash
ansible-galaxy collection install git@github.com:techprober/galaxy-collections#/collections/ansible_collections/techprober/apt,master
```

You can also include it in a `requirements.yml` file and install it with `ansible-galaxy collection install -r requirements.yml`, using the format:

```yaml
collections:
  - name: git@github.com:techprober/galaxy-collections#/collections/ansible_collections/techprober/apt
    type: git
    version: master
```

To install a specific version of the collection, using the format:

```yaml
collections:
  - name: git@github.com:techprober/galaxy-collections#/collections/ansible_collections/techprober/apt
    type: git
    version: techprober.apt.v1.0.0
```

Upgrade the exiting collection with the following command:

```bash
ansible-galaxy collection install -r requirements.yml --upgrade
```

## Use this collection

After installing the collection, you may directly use the roles in your playbook.

```yaml
# update-apt-packages
---
- name: Upgrade remote server
  hosts: all
  become: yes

  roles:
    - role: techprober.apt.update
      vars:
        - dist_upgrade: false # set this var to true will perform dist upgrade
```

## Contribute to this collection

We welcome community contributions to this collection. If you find problems, please open an issue or create a PR against the [techprober/galaxy-collections](https://github.com/techprober/galaxy-collections) repository. See [How to Contribute](https://github.com/techprober/galaxy-collections/blob/master/docs/contribute.md) for more details.

## License

[MIT (C) TechProber](https://github.com/yqlbu/TechProber/galaxy-collections/blob/master/LICENSE)
