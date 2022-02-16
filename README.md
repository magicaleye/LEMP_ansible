# Setup LEMP stack using ansible

- Settings up Ansible control node
  1. Update packages using yum/apt
     - sudo yum/apt update
     - (CentOS host) sudo yum install -y epel-release
     - Install ansible : sudo yum/apt install -y ansible
  2. Generate ssh key: ssh-keygen
  3. Copy key to hosts
     - ssh-copy-id root@192.168.10.101
     - ssh-copy-id root@192.168.10.102
     - ssh-copy-id root@192.168.10.103
  4. Enable ssh using root (Ubuntu)
     - vim /etc/ssh/sshd_config
     - Change PermitRootLogin to yes
     - Restart sshd service: systemctl restart sshd
- Settings up Ansible hosts VM

  - OS : CentOS 7, IP Address: 192.168.10.101
  - OS : CentOS 7, IP Address: 192.168.10.102
  - OS : Ubuntu 20.04, IP Address: 192.168.10.103

- Run command:
  - ansible-playbook Playbook.yml
