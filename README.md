GRE for Ubuntu
=================

Role for establish gre tunnels on Ubuntu 16.04/18.04
Also sysctl vars will be changed:

```
net.ipv4.conf.default.rp_filter -> 0
net.ipv4.conf.all.rp_filter -> 0
net.ipv4.ip_forward -> 1
```

### Defaults
```
gre_parent_iface: eth0
gre_remote_ip: ''
gre_local_ip: ''
gre_ip_addr: ''
gre_interface: gre1
```

GRE tunnel is disabled by default. Please use gre_enable for enabling tunnel

### Example playbook
```
- hosts: all
  become: yes
  gather_facts: yes
  roles:
    - { role: ansible-gre, gre_enable: true }

```
