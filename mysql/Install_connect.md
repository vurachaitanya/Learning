### Ansible to install MYSQL:

```
---
- name: Install MySQL
  hosts: chaitu
  become: true
  remote_user: root
  become_method: sudo
  gather_facts: true
  tasks:
    - name: "Installing Repo for Centos 7.9"
      shell: sudo rpm -Uvh https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
      ignore_errors: yes
    - name: "Installing MySQL 5.7"
      package: name=mysql-community-server state=present
    - name: Start the MySQL service
      become: true
      service: 
        name: mysqld
        state: started
        enabled: true
    - name: Find MySQL root password
      shell: "echo `grep 'temporary.*root@localhost' /var/log/mysqld.log | sed 's/.*root@localhost: //'`"
      register: mysql_root_pass
    - debug: var=mysql_root_pass.stdout
```
- `mysql -u root -p` command to connect to mysql DB.
- 
