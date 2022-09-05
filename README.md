# Ansible
Repo for Ansible stuff..

## Ansible inventory
It may contain information such as Host IPs, DNS Name, SSH User and Pass, SSH Port service info (in case it is other than port 22).

The default location for inventory is 
```
/etc/ansible/hosts
```

It may contain information in following format:
```
[webservers]
www.example1.com
www.example2.com
[dbservers]
192.x.x.x
10.x.x.x
```

----
### Creating custom inventory file:
First disable the host key checking. To do so, make a change in ansible configuration file which is located at 
```
/etc/ansible/ansible.cfg
```



