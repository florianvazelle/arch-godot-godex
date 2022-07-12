# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "arch"
    config.vm.define "arch-godot-godex"
  
    # Share an additional folder to the guest VM.
    config.vm.synced_folder "./data", "/vagrant_data"
  
    # Provider-specific configuration.
    config.vm.provider "virtualbox" do |vb|
      # Display the VirtualBox GUI when booting the machine
      vb.gui = true
    
      # Customize the amount of memory on the VM:
      vb.memory = "4096"
      
      # Customize the amount of CPU on the VM:
      vb.cpus = 2
    end

    # SSH credentials.
    config.ssh.username = "vagrant"
    config.ssh.password = "vagrant"
  
    # Enable provisioning with a shell script.
    config.vm.provision "shell", inline: <<-SHELL
      pacman -Syu scons godot --noconfirm
    SHELL
  end