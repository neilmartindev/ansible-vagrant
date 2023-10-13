# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.

  # CentOS 8 VM configuration
  config.vm.define "centos8_vm" do |centos8|
    centos8.vm.box = "centos/8"  # Adjust if you have a different box name for CentOS 8 with libvirt
    centos8.vm.hostname = "centos8.local"
    centos8.vm.network "private_network", type: "dhcp"
    
    centos8.vm.provider :libvirt do |libvirt|
      libvirt.memory = 2048  # 2 GB RAM
      libvirt.cpus = 2       # 2 CPUs
    end
  end

  # Rocky Linux 9 VM configuration
  config.vm.define "rocky9_vm" do |rocky9|
    rocky9.vm.box = "rockylinux/9"  # Adjust if you have a different box name for Rocky Linux 9 with libvirt
    rocky9.vm.hostname = "rocky9.local"
    rocky9.vm.network "private_network", type: "dhcp"
    
    rocky9.vm.provider :libvirt do |libvirt|
      libvirt.memory = 2048  # 2 GB RAM
      libvirt.cpus = 2       # 2 CPUs
    end

    rocky9.vm.provision "ansible" do |ansible|
      ansible.playbook = "install_lamp.yaml"
      # additional ansible configurations for Rocky Linux 9 if needed
    end
  end

  # Additional configurations can be added here. Examples are commented below:

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # ... other configurations ...

end
