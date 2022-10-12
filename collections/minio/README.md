# TechProber Minio Collection

The `techprober-minio-collection` includes a variety of Ansible content to help automate the management of package managements for servers that are based on the `debian` system. This collection is maintained by the techprober core team.

## Ansible version compatibility

Tested with the Ansible Core `2.8`, `2.12`, and `2.13` releases, and the current development version of Ansible.

## Install this collection

You can install the `techprober.minio` collection with the Ansible Galaxy CLI:

```bash
ansible-galaxy collection install git@github.com:techprober/galaxy-collections#/collections/ansible_collections/techprober/minio,master
```

You can also include it in a `requirements.yml` file and install it with `ansible-galaxy collection install -r requirements.yml`, using the format:

```yaml
# requirements.yml
---
collections:
  - name: git+https://github.com/techprober/galaxy-collections.git#/collections/ansible_collections/techprober/minio
    type: git
    version: master
```

To install a specific version of the collection, using the format:

```yaml
# requirements.yml
---
collections:
  - name: git+https://github.com/techprober/galaxy-collections.git#/collections/ansible_collections/techprober/minio
    type: git
    version: techprober.minio.v1.0.0
```

Upgrade the exiting collection with the following command:

```bash
ansible-galaxy collection install -r requirements.yml --upgrade
```

## Use this collection

After installing the collection, you may directly use the roles in your playbook.

```yaml
# setup-minio.yml
---
- name: Setup Minio Connection
  hosts: all
  become: yes

  roles:
    - role: techprober.minio.setup
      vars:
        - home_user: "packer"
        - minio_remote_url: "http://10.178.0.9:9000"
        - minio_access_key: !vault |
            $ANSIBLE_VAULT;1.1;AES256
            31396530623066303630646663386565306137636336663830383464393334326530633762666664
            3962363938616234313436393666346430383961313162300a353062313465613462663636643535
            61656237633362626431313631646563626263323836376339313331616562333361383230623435
            6530333537376165380a343535386239356638643034613732373461333865343164626563666531
            65383133666431343730326334353936636364323535653630633965346362386233
        - minio_secret_key: !vault |
            $ANSIBLE_VAULT;1.1;AES256
            33316132633937373163353439326630656539343435346436626534353936386538653761663466
            6439383566616339346330393264313238373561653966360a393665643334646235633738613037
            34623134653866313634633738393062343461656531326630316430396432643531353661346239
            3436383433323962310a333064336631383761643163636565346364613664396361636533636466
            32613039633839306537333331343234316139383432353465333734313561373437366235613636
            3561306639656235626665626338646331643637613061396361
```

## Contribute to this collection

We welcome community contributions to this collection. If you find problems, please open an issue or create a PR against the [techprober/galaxy-collections](https://github.com/techprober/galaxy-collections) repository. See [How to Contribute](https://github.com/techprober/galaxy-collections/blob/master/docs/contribute.md) for more details.

## License

[MIT (C) TechProber](https://github.com/yqlbu/TechProber/galaxy-collections/blob/master/LICENSE)
