# Uninstalling glusterfs
ansible-playbook --inventory-file=inventory.ini playbooks/uninstall-gluster.yml --ask-become-pass --ask-pass

# Installing glusterfs
ansible-playbook --inventory-file=inventory.ini playbooks/install.yml --ask-become-pass --ask-pass

# Fixing apt upgrade error on download.gluster.com pub key
ansible all -i inventory.ini -b -m shell -a "umount /srv/gluster" --ask-become-pass --ask-pass

--start-at-task="Task Name"

# Checking hosts of ansible
ansible all -i inventory.ini -m ping

# Deleting mount path of gluster volume
ansible all -i inventory.ini -b -m shell -a "umount /srv/gluster" --ask-become-pass --ask-pass
ansible all -i inventory.ini -b -m shell -a "rm -rf /srv/gluster" --ask-become-pass --ask-pass

-------------------------------------------------------------------------------------
# Glusterfs for vagrant
ansible-playbook --inventory-file=hosts-vagrant playbooks/install4vagrant.yml
ansible all -i hosts-vagrant -m ping
ansible all -i hosts-vagrant -b -m shell -a "apt upgrade -y"

# To ssh into virtualbox machines
ssh -i ~/.vagrant.d/insecure_private_key  vagrant@192.168.56.30

# Uninstalling glusterfs
ansible-playbook --inventory-file=hosts-vagrant playbooks/uninstall-gluster.yml
=======
ansible-playbook --inventory-file=hosts-vagrant playbooks/uninstall-gluster.yml

# Installing all stacks
ansible-playbook --inventory-file=hosts-vagrant playbooks/install.yml

ansible-playbook --inventory-file=hosts-vagrant playbooks/install.yml --start-at-task="Task Name"

# Checking hosts of ansible
ansible all -i hosts -m ping

# For vagrant
ansible-playbook --inventory-file=hosts-vagrant playbooks/install.yml
ansible all -i hosts-vagrant -m ping

# To ssh into virtualbox machines
ssh -i ~/.vagrant.d/insecure_private_key  vagrant@192.168.56.30

# Fixing apt upgrade error on download.gluster.com pub key
ansible all -i hosts-vagrant -b -m shell -a "wget -O - https://download.gluster.org/pub/gluster/glusterfs/10/rsa.pub | apt-key add -"