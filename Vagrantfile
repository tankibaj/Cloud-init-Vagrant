# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.env.enable # enable .env support plugin (it will let us easily enable cloud_init support)

  
  
  #------ VM Box Settings ------#
  # Name for the box image downloaded from the box_url
  # It will be used to create a folder inside ~/.vagrant.d/boxes to avoid re-downloading
  config.vm.box = "focal-server-cloudimg-amd64-vagrant"

  # URL used as a source for the vm.box defined above
  config.vm.box_url = "https://cloud-images.ubuntu.com/focal/current/focal-server-cloudimg-amd64-vagrant.box"

  
  
  #------ VM Provider Settings ------#
  config.vm.provider "virtualbox" do |vb|
    vb.name = "cloud-images"
    vb.gui = false            # Display the VirtualBox GUI when booting the machine
    vb.memory = "1024"        # Customize the amount of memory on the VM
    #vb.cpus = 4              # Customize the amount of cpu on the VM
  end

  
  
  #------ Network Settings ------#
  #config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"  # Create a forwarded port mapping which allows access to a specific port
  config.vm.network "private_network", ip: "10.0.0.20"                              # Create a private network, which allows host-only access to the machine using a specific IP.
  #config.vm.network "public_network"                                               # Create a public network, which generally matched to bridged network.

  
  
  #------ Folder Settings ------#
  config.vm.synced_folder "./workspace", "/home/naim/workspace", type: "nfs", id: "workspace"  # Share an additional folder to the guest VM.
  
  
  
  #------ Provisioning Settings ------#
  # cloud-init script
  config.vm.cloud_init :user_data do |cloud_init|
    cloud_init.content_type = "text/cloud-config"
    cloud_init.path = "./user-data.yml"
  end
 
end
