$script = <<-'SCRIPT'
export DEBIAN_FRONTEND=noninteractive
apt-get -y remove grub-pc
apt-get -y install grub-pc
grub-install /dev/sda1 # precaution
update-grub 
# now start bootstrapping and upgrading your system packages
apt-get -y update
apt-get -y upgrade
SCRIPT

Vagrant.configure("2") do |config|
  config.ssh.insert_key = false

  config.vm.define "docker01" do |docker01|
    docker01.vm.box = "debian/buster64"
    docker01.vm.box_version = "10.4.0"
    docker01.vm.hostname = "docker01"
    docker01.vm.network "private_network", ip: "192.168.56.10", netmask: "255.255.255.0"
    docker01.disksize.size = '20GB'
    docker01.vm.provision "shell", inline: $script

    # virtualbox setup
    docker01.vm.provider "virtualbox" do |vb|
      vb.name = "docker01"

      # Set CPU and Ram
      vb.customize ["modifyvm", :id, "--cpus", "1"]
      vb.customize ["modifyvm", :id, "--memory", "1024"]

      # Get disk path
      line = `VBoxManage list systemproperties | grep "Default machine folder"`
      vb_machine_folder = line.split(':')[1].strip()
      second_disk = File.join(vb_machine_folder, vb.name, 'disk2.vdi')

      # Create disk
      unless File.exist?(second_disk)
        vb.customize ['createmedium', 'disk', '--filename', second_disk, '--size', 10 * 1024]
      end

      # Attach disk to VM
      vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 2, '--type', 'hdd', '--medium', second_disk]
    end
  end

  config.vm.define "docker02" do |docker02|
    docker02.vm.box = "debian/buster64"
    docker02.vm.box_version = "10.4.0"
    docker02.vm.hostname = "docker02"
    docker02.vm.network "private_network", ip: "192.168.56.20", netmask: "255.255.255.0"
    docker02.disksize.size = '20GB'
    docker02.vm.provision "shell", inline: $script

    # virtualbox setup
    docker02.vm.provider "virtualbox" do |vb|
      vb.name = "docker02"

      # Set CPU and Ram
      vb.customize ["modifyvm", :id, "--cpus", "1"]
      vb.customize ["modifyvm", :id, "--memory", "1024"]

      # Get disk path
      line = `VBoxManage list systemproperties | grep "Default machine folder"`
      vb_machine_folder = line.split(':')[1].strip()
      second_disk = File.join(vb_machine_folder, vb.name, 'disk2.vdi')

      # Create disk
      unless File.exist?(second_disk)
        vb.customize ['createmedium', 'disk', '--filename', second_disk, '--size', 10 * 1024]
      end

      # Attach disk to VM
      vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 2, '--type', 'hdd', '--medium', second_disk]
    end
  end

  config.vm.define "docker03" do |docker03|
    docker03.vm.box = "debian/buster64"
    docker03.vm.box_version = "10.4.0"
    docker03.vm.hostname = "docker03"
    docker03.vm.network "private_network", ip: "192.168.56.30", netmask: "255.255.255.0"
    docker03.disksize.size = '20GB'
    docker03.vm.provision "shell", inline: $script

    # virtualbox setup
    docker03.vm.provider "virtualbox" do |vb|
      vb.name = "docker03"

      # Set CPU and Ram
      vb.customize ["modifyvm", :id, "--cpus", "1"]
      vb.customize ["modifyvm", :id, "--memory", "1024"]

      # Get disk path
      line = `VBoxManage list systemproperties | grep "Default machine folder"`
      vb_machine_folder = line.split(':')[1].strip()
      second_disk = File.join(vb_machine_folder, vb.name, 'disk2.vdi')

      # Create disk
      unless File.exist?(second_disk)
        vb.customize ['createmedium', 'disk', '--filename', second_disk, '--size', 10 * 1024]
      end

      # Attach disk to VM
      vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 2, '--type', 'hdd', '--medium', second_disk]
    end
  end
  config.vm.define "docker04" do |docker04|
    docker04.vm.box = "debian/buster64"
    docker04.vm.box_version = "10.4.0"
    docker04.vm.hostname = "docker04"
    docker04.vm.network "private_network", ip: "192.168.56.40", netmask: "255.255.255.0"
    docker04.disksize.size = '20GB'
    docker04.vm.provision "shell", inline: $script

    # virtualbox setup
    docker04.vm.provider "virtualbox" do |vb|
      vb.name = "docker04"

      # Set CPU and Ram
      vb.customize ["modifyvm", :id, "--cpus", "1"]
      vb.customize ["modifyvm", :id, "--memory", "1024"]

      # Get disk path
      line = `VBoxManage list systemproperties | grep "Default machine folder"`
      vb_machine_folder = line.split(':')[1].strip()
      second_disk = File.join(vb_machine_folder, vb.name, 'disk2.vdi')

      # Create disk
      unless File.exist?(second_disk)
        vb.customize ['createmedium', 'disk', '--filename', second_disk, '--size', 10 * 1024]
      end

      # Attach disk to VM
      vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 2, '--type', 'hdd', '--medium', second_disk]
    end
  end
  config.vm.define "docker05" do |docker05|
    docker05.vm.box = "debian/buster64"
    docker05.vm.box_version = "10.4.0"
    docker05.vm.hostname = "docker05"
    docker05.vm.network "private_network", ip: "192.168.56.50", netmask: "255.255.255.0"
    docker05.disksize.size = '20GB'
    docker05.vm.provision "shell", inline: $script

    # virtualbox setup
    docker05.vm.provider "virtualbox" do |vb|
      vb.name = "docker05"

      # Set CPU and Ram
      vb.customize ["modifyvm", :id, "--cpus", "1"]
      vb.customize ["modifyvm", :id, "--memory", "1024"]

      # Get disk path
      line = `VBoxManage list systemproperties | grep "Default machine folder"`
      vb_machine_folder = line.split(':')[1].strip()
      second_disk = File.join(vb_machine_folder, vb.name, 'disk2.vdi')

      # Create disk
      unless File.exist?(second_disk)
        vb.customize ['createmedium', 'disk', '--filename', second_disk, '--size', 10 * 1024]
      end

      # Attach disk to VM
      vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 2, '--type', 'hdd', '--medium', second_disk]
    end
  end

end

