# Ansible Collection Role: techprober.minio.setup

An Ansible Role to setup minio client and configure connection for any linux distributions

## Requirements

None.

## Dependencies

None.

## Role Variables

Default home_user to configure minio connection

```yaml
home_user: "<home_user>"
```

The url of fqdn of the remote minio server

```yaml
minio_remote_url: "http://<host_ip>:9000"
```

The user access key used to connect to the minio server, better use ansible-vault to encrypt

```yaml
minio_access_key: "<access_key>"
```

The user secret key used to connect to the minio server, better use ansible-vault to encrypt

```yaml
minio_secret_key: "<secret_key>"
```

## Example Playbook

```yaml
- name: Setup Minio Connection
  hosts: all
  become: yes

  roles:
    - role: techprober.apt.update
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

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Kevin Yu](https://github.com/yqlbu)
