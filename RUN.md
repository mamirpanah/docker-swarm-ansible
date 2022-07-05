# Uninstalling glusterfs
ansible-playbook --inventory-file=hosts playbooks/uninstall-gluster.yml

# Installing glusterfs
ansible-playbook --inventory-file=hosts playbooks/install.yml

# Checking hosts of ansible
ansible all -i hosts -m ping

# Deleting mount path of gluster volume
ansible all -i hosts -b -m shell -a "umount /srv/gluster" --ask-become-pass --ask-pass
ansible all -i hosts -b -m shell -a "rm -rf /srv/gluster" --ask-become-pass --ask-pass

# For vagrant
ansible-playbook --inventory-file=hosts-vagrant playbooks/install.yml
ansible all -i hosts-vagrant -m ping

# To ssh into virtualbox machines
ssh -i ~/.vagrant.d/insecure_private_key  vagrant@192.168.56.30