# ansible-playbook-kubernetes-cluster
Ansible playbook for kubernetes cluster which works on Rocky/Ubuntu/CentOS
sve radimo na user-u aca
ssh-keygen -t ed25519 -C "my default key" 
ssh-copy-id -i ~/.ssh/id_ed25519.pub 192.168.122.249
ssh-copy-id -i ~/.ssh/id_ed25519.pub 192.168.122.76

sudo nano /etc/ssh/sshd_config
trazimo ovo  #PubkeyAuthentication yes i uklanjamo tarabu

git clone https://github.com/mcpalek/ansible-playbook-kubernetes-cluster.git
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

ansible-playbook local.yml --key-file ~/.ssh/id_ed25519 --ask-become-pass  ovo je lozinka koja je validna na svim serverima