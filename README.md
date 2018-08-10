## Deploy vagrant  

- - - -  
#### Version dependency  
1. Ansible: `2.5.1`  
2. Python:  `2.7.5`,`2.7.10`,`3.6.5`  


- - - -  
#### Role dependency  
```
None
```


- - - -  
#### VARS  
Inside `group_vars/hostgroup.yml`  
```
# roles/ansible-role-os-setup
# MySQL
mysql_home_dir: "/usr/local/mysql"

# MHA
mha_home_dir: "/usr/local/mha"

# TD-AGENT
td_agent_home_dir: "/home/td-agent"
```


- - - -  
#### Playbook example  


```yml
---
- hosts: vagrant
  become: yes

  roles:
    - ansible-role-os-setup
```
