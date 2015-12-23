# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  
  config.vm.box = "nrel/CentOS-6.5-x86_64"
  config.vbguest.auto_update = false
  config.vm.provision "file", source: "/opt/vms/vagrant/files/git-config", destination: "~/.gitconfig"
  config.vm.provision "shell", path: "https://raw/githubusercontent.com/inthebackofmymind/vagrant/master/files/multiple.sh"
  
  config.omnibus.chef_version = :latest

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.provision "chef_solo" do |chef|
    chef.cookbooks_path = "/opt/vms/vagrant/chef/supermarket"
    chef.add_recipe "java"
    chef.json = {
	"java" => {
	  "jdk_version" => "7"
	}
    }
  end

end
