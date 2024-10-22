# enix.ucarp for Ansible
![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

A role for deploying and configuring [ucarp](https://www.pureftpd.org/project/ucarp) on unix hosts using [Ansible](http://www.ansible.com/).


Requirements
------------

Supported targets:

- Ubuntu 14.04 "Trusty"
- Ubuntu 16.04 "Xenial"
- Ubuntu 18.04 "Bionic"
- Debian 8 "Jessie"
- Debian 8 "Stretch"

Role Variables
--------------

This roles comes preloaded with almost every available default. You can override each one in your hosts/group vars, in your inventory, or in your play. See the annotated defaults in `defaults/main.yml` for help in configuration. All provided variables start with `ucarp__`.

- `ucarp__interface` - *mandatory*, network interface on which ucarp should bind on; will fail if none defined, `default: none`.
- `ucarp__interface_configfile` - configuration file where ucarp__interface defined, `default: /etc/network/interfaces`.
- `ucarp__vid` - id of the ucarp setup, `default: 10`.
- `ucarp__vip` - *mandatory*, virtual ip address, `default: none`.
- `ucarp__vip_netmask` - virtual ip netmask, `default: 255.255.255.255`.
- `ucarp__vip_upaction` - up action in interface configuration, `default: none`.
- `ucarp__vip_downaction` - down action in interface configuration, `default: none`.
- `ucarp__password` - *mandatory*, password used to auth ucarp processes, `default: none`.
- `ucarp__advskew` - advskew parameter, `default: 0`.
- `ucarp__advbase` - advbase parameter, `default: 1`.
- `ucarp__master` - make this host master by default (preempt mode), `default: no`

Dependencies
------------

- The network interface used to provide the ucarp communication and configuration between the different hosts must be statically configured. dhcp interfaces are not supported by ucarp Debian up-scripts because it use the address configured to start the ucarp daemon

Usage
-----

Use Ansible galaxy requirements.yml

    # enix.ucarp galaxy role
    - src: enix.ucarp
      name: ucarp

And add it to your play's roles:

    - hosts: servers
      roles:
        - role: ucarp
          - ucarp__

You can also use the role as a playbook. You will be asked which hosts to provision, and you can further configure the play by using `--extra-vars`.

    $ ansible-playbook -i inventory --extra-vars='{...}' main.yml


Still to do
-----------

- ...


# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
