# Ansible
Repo for Ansible stuff..

## Ansible inventory
It may contain information such as Host IPs, DNS Name, SSH User and Pass, SSH Port service info (in case it is other than port 22).

The default location for inventory is -
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

---
### Creating custom inventory file:
a. Disable the host key checking:
To do so, make a change in ansible configuration file which is located at -
```
sudo vim /etc/ansible/ansible.cfg
```
Uncomment the line: host_key_checking = False

b. Create inventory file:
In /etc/ansible/ directory, and create inventory.txt file, and add below details to it:
```
<host_alias> ansible_host=<host_pvt_ip> ansible_ssh_pass=password ansible_connection=ssh ansible_port=22 ansible_user=root 
```

