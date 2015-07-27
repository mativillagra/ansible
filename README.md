# ansible

ansible 1.7.2

ansible windows -i host -m win_ping

ansible winhost.example.com -m setup

ansible-playbook -i /home/matiasvx/ansible_test/host  msi.yml

http://docs.ansible.com/win_copy_module.html


################################################################################

SETUP 

1. matiasvx@debian:~$ cp ~/.ssh/id_rsa.pub /home/matiasvx/ansible_test/files/debian.pub

2. ansible-playbook -i ../linux key.yml --ask-pass

key.yml 

---
- hosts: linux
  sudo : yes
  tasks:

       - authorized_key: user=perinola key="{{ lookup('file', "../files/debian.pub") }}

3. This will should not ask you for a password : ansible-playbook -i ../linux copy.yml 

4. Another example : ansible -i linux st-per-ml2-vl23.asdc.lab  -m shell -a "uptime"

5. cd /home/matiasvx/ansible_test/playbooks && /usr/bin/ansible-playbook -i ../linux mar.yml --extra-vars target=${option.command} Rundeck Job 

Fuente: http://thornelabs.net/2014/03/08/install-ansible-create-your-inventory-file-and-run-an-ansible-playbook-and-some-ansible-commands.html

