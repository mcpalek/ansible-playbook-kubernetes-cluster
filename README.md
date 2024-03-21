# ansible-playbook-kubernetes-cluster

pre-req

sudo visudo 
aca ALL=(ALL) NOPASSWD:ALL


Ansible playbook for kubernetes cluster which works on Rocky/Ubuntu/CentOS
sve radimo na user-u aca
ssh-keygen -t ed25519 -C "my default key" 
ssh-keygen -t ed25519 -C "ansible"   /home/aca/.ssh/ansible

ssh-copy-id -i ~/.ssh/ansible.pub aca@192.168.122.249
ssh-copy-id -i ~/.ssh/ansible.pub aca@192.168.122.76

cat ~/.ssh/ansible.pub | ssh aca@192.168.122.75 "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

ssh-copy-id -i ~/.ssh/id_ed25519.pub 192.168.122.249
ssh-copy-id -i ~/.ssh/id_ed25519.pub 192.168.122.76

sudo nano /etc/ssh/sshd_config
trazimo ovo  #PubkeyAuthentication yes i uklanjamo tarabu
PasswordAuthentication no
ChallengeResponseAuthentication no
sudo nano /etc/ssh/sshd_config.d/50-cloud-init.conf
PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM no


git clone https://github.com/mcpalek/ansible-playbook-kubernetes-cluster.git
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

eval $(ssh-agent)
ssh-add ~/.ssh/id_ed25519
ssh-add ~/.ssh/ansible
ansible all -m ping --key-file ~/.ssh/ansible --ask-become-pass
ansible all -m ping --key-file ~/.ssh/d_ed25519
ansible-playbook local.yml --key-file ~/.ssh/ansible --ask-become-pass  ovo je lozinka koja je validna na svim serverima

ansible-playbook local.yml --key-file ~/.ssh/id_ed25519 --ask-become-pass  ovo je lozinka koja je validna na svim serverima