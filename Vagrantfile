# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "https://vagrant-osx.nyc3.digitaloceanspaces.com/osx-sierra-0.3.1.box"

  config.vm.network "private_network", ip: "192.168.99.33"

  config.vm.synced_folder "/home/paoc/Dropbox/Diagrams", "/diagrams",
    id: "diagrams-folder",
    :nfs => true,
    :mount_options => ['nolock,vers=3,udp,noatime,actimeo=1,resvport'],
    :export_options => ['async,insecure,no_subtree_check,no_acl,no_root_squash']

  config.vm.provider "virtualbox" do |v|
    v.gui = true
    v.memory = 4096
    v.cpus = 4
    v.customize ["modifyvm", :id, "--vram", "128"]
    v.customize ["setextradata", :id, "VBoxInternal2/EfiGraphicsResolution", "1440x900x32"]
    v.customize ["modifyvm", :id, "--accelerate3d", "on"]
    v.customize ["modifyvm", :id, "--hwvirtex", "on"]
  end
  
end
