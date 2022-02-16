# Setup LEMP stack using ansible

- Centos 7 username: root
- Ubuntu server username: ubuntu

Ansible hosts:
[centos7]
192.168.10.101
192.168.10.102

[ubuntu]
192.168.10.103

Check connection
ansible centos7 -m ping -u root
ansible ubuntu -m ping -u ubuntu
