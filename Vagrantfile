# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  
  config.vm.box = "nrel/CentOS-6.5-x86_64"
  config.vbguest.auto_update = false
  config.vm.provision "file", source: "/opt/vms/vagrant/files/git-config", destination: "~/.gitconfig"
  config.vm.provision "shell", path: "https://raw/githubusercontent.com/inthebackofmymind/

end
