# ansible-playbook-kubernetes-cluster



Ansible playbook for kubernetes cluster which works on Rocky/Ubuntu/CentOS and RedHat

I am using user-u aca

ssh-keygen -t ed25519 -C "ansible"   # here I write /home/aca/.ssh/ansible for the folder in which I am saving the ssh key

ssh-copy-id -i ~/.ssh/ansible.pub aca@192.168.1.38    # here you write the IP of the vm where you copy 

ssh-copy-id -i ~/.ssh/ansible.pub aca@192.168.1.37    # here you write the IP of the vm where you copy


ansible all -m ping --key-file ~/.ssh/ansible --ask-become-pass  # with this command we are cheking if all virtual machines are accessible

ansible-playbook local.yml --key-file ~/.ssh/ansible --ask-become-pass  # with this command you start the playbook
