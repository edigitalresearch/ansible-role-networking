# Ansible Role - Networking

An Ansible Role for configuring network interfaces

# Variables

Here is an example variables file for setting a static IP address - Additional networking interface properties can be added as needed: [https://www.centos.org/docs/5/html/Deployment_Guide-en-US/s1-networkscripts-interfaces.html](https://www.centos.org/docs/5/html/Deployment_Guide-en-US/s1-networkscripts-interfaces.html)

```
networking:
  interfaces:
    ens33:
      DNS1: 8.8.8.8
      IPADDR: 192.168.0.5
      GATEWAY: 192.168.0.1
      NETMASK: 255.555.255.0
      BOOTPROTO: static
      ONBOOT: "yes"
      IPV6INIT: "yes"
      DEVICE: ens33
```

# Example Task with role

```
- name: Networking | Configure Interfaces
  hosts: all
  roles:
    - edr.networking
```
