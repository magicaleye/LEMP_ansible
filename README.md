# Setup LEMP stack using ansible

- Settings up VM

1. Control node
   - OS : CentOS 7, IP Address: 192.168.10.100
2. Hosts
   - OS : CentOS 7, IP Address: 192.168.10.101
   - OS : CentOS 7, IP Address: 192.168.10.102
   - OS : Ubuntu 20.04, IP Address: 192.168.10.103

- Settings up Ansible control node
  1. Edit Ansible hosts file on Control node
      [centos7]
      192.168.10.101
      192.168.10.102
   
      [ubuntu]
      192.168.10.103
  2. Update packages using yum/apt (All VMs)
     - sudo yum/apt update
     - sudo yum/apt upgrade -y
     - (CentOS host) sudo yum install -y epel-release
     - Install ansible : sudo yum/apt install -y ansible
  3. Generate ssh key: ssh-keygen (Control node)
  4. Copy key to hosts (Control node)
     - ssh-copy-id root@192.168.10.101
     - ssh-copy-id root@192.168.10.102
     - ssh-copy-id root@192.168.10.103
  5. Enable ssh using root (Ubuntu host)
     - vim /etc/ssh/sshd_config
     - Change PermitRootLogin to yes
     - Restart sshd service: systemctl restart sshd

- Run command:
  - ansible-playbook Playbook.yml
