# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  #
  # Configure Kali Linux
  #
  config.vm.define "kali", primary: true do |kali|
    kali.vm.box = "kalilinux/rolling"

    kali.vm.network "private_network", ip: "172.28.128.10"

    kali.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.customize ["modifyvm", :id, "--memory", 1024]
      vb.customize ["modifyvm", :id, "--cpus", 1]
      vb.customize ["modifyvm", :id, "--vram", "128"]
      vb.customize ["setextradata", "global", "GUI/MaxGuestResolution", "any"]
      vb.customize ["setextradata", :id, "CustomVideoMode1", "1024x768x32"]
      vb.customize ["modifyvm", :id, "--ioapic", "on"]
      vb.customize ["modifyvm", :id, "--rtcuseutc", "on"]
      vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
      vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    end

    # kali.vm.provision "shell", inline: <<-SHELL
    #   apt-get update
    #   apt-get install -y task-japanese task-japanese-desktop
    # SHELL
  end

  #
  # Configure Windows 10
  #
  # Requires Windows image:
  # 1. Download the vagrant box image: https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/
  # 2. unzip MSEdge.Win10.Vagrant.zip
  # 3. vagrant box add EdgeOnWindows10.box --name windows10
  #
  config.vm.define "windows10", autostart: false do |win|
    win.vm.box = "windows10"

    win.vm.network "private_network", ip: "172.28.128.11"

    win.vm.guest = "windows"
    win.vm.communicator = "winrm"
    win.winrm.username = "IEUser"
    win.winrm.password = "Passw0rd!"

    win.vm.synced_folder ".", "/vagrant", disabled: true
    win.vm.synced_folder ".", "C:\\vagrant"

    win.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.customize ["modifyvm", :id, "--memory", 1536]
      vb.customize ["modifyvm", :id, "--cpus", 1]
      vb.customize ["modifyvm", :id, "--vram", "128"]
      vb.customize ["setextradata", "global", "GUI/MaxGuestResolution", "any"]
      vb.customize ["setextradata", :id, "CustomVideoMode1", "1024x768x32"]
    end
  end
end
