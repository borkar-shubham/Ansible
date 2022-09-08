# Ansible
Topics:
* a. Ansible Galaxy
* b. Asynchronous Action
* c. Error Handling
* d. Jinja2 Templating
* e. Lookups
* f. Vaults
* g. Dynamic Inventory
* h. Custom Module
* i. Plugins, register vars
* j. Conditions when (and/or), Setfacts, loops, privilege escalation, tags
---
Installing Ansible on Ubuntu
```
$ sudo apt update
$ sudo apt install software-properties-common -y
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible -y
```
Installing Ansible on CentOS
```
$ sudo yum install epel-release
$ sudo yum install ansible
```
---

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
In /etc/ansible/ directory, and create inventory file, and add below details to it:
```
<host_alias> ansible_host=<host_pvt_ip> ansible_ssh_pass=<password> ansible_connection=ssh ansible_port=22 ansible_user=<user> 
```
To mention the custom inventory configuration, include it in ansible command as follows -
```
$ ansible webserver1 -m ping -i inventory
