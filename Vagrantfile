Vagrant.configure("2") do |config|
    # Configuration for the Ubuntu VM
    config.vm.define "ubuntu_vm" do |ubuntu|
      ubuntu.vm.box = "ubuntu/focal64"
      ubuntu.vm.network "private_network",  ip:"192.168.56.91"
      ubuntu.vm.hostname = "ubuntu-vm"
      ubuntu.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 2
      end
      ubuntu.vm.provision "shell", inline: <<-SHELL
        echo "Ubuntu VM is running"
      SHELL
    end
  
    # Configuration for the CentOS VM
    config.vm.define "centos_vm" do |centos|
      centos.vm.box = "centos/stream9"
      centos.vm.network "private_network", ip:"192.168.56.92"
      centos.vm.hostname = "centos-vm"
      centos.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 2
      end
      centos.vm.provision "shell", inline: <<-SHELL
        echo "CentOS VM is running"
      SHELL
    end

      # Configuration for the Another Debian VM

    config.vm.define "debian_vm" do |debian|
      debian.vm.box = "debian/buster64"
      debian.vm.network "private_network",  ip:"192.168.56.93"
      debian.vm.hostname = "debian-vm"
      debian.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 2
      end
      debian.vm.provision "shell", inline: <<-SHELL
      apt install mariadb-server -y
      systemctl start mariadb
        echo "Debian VM is running"

      SHELL
    end
  end
  