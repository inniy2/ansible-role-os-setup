## Deploy vagrant  

- - - -  
#### Version dependency  
1. Ansible: `2.5.1`
2. Python:  `3.6.5`


- - - -  
#### Role dependency  
```
None
```


- - - -  
#### VARS
inside `group_vars/hostgroup.yml`

```
---
# MySQL
mysql_download_version: "mysql-5.7.18-linux-glibc2.5-x86_64"

mysql_root_db_pass: XXXXXXXX

mysql_instance_name: "cloud101"

mysql_port: 3301

mysql_bind_address: "0.0.0.0"

mysql_instance_dir: "/MYSQL/{{ mysql_instance_name }}"

mysql_conf_dir: "{{ mysql_instance_dir }}/var"

mysql_conf_file: "my_{{ mysql_instance_name }}.cnf"

mysql_socket: "/usr/local/mysql/sock/{{ mysql_instance_name }}.sock"

mysql_client: "{{ mysql_instance_dir }}/product/bin/mysql"

mysql_home_dir: "/usr/local/mysql"


# MHA
mha_home_dir: "/usr/local/mha"
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
