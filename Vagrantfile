# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise64"

  config.vm.define :web1 do |machine|
    machine.vm.hostname = 'web1'
    machine.vm.network "private_network", ip: "192.168.33.11"
  end

  config.vm.define :web2 do |machine|
    machine.vm.hostname = 'web2'
    machine.vm.network "private_network", ip: "192.168.33.12"
  end

  config.vm.define :db1 do |machine|
    machine.vm.hostname = 'db1'
    machine.vm.network "private_network", ip: "192.168.33.13"
  end

  config.vm.define :lb1 do |machine|
    machine.vm.hostname = 'lb1'
    machine.vm.network "private_network", ip: "192.168.33.10"

	  machine.vm.provision :ansible do |ansible|
	  	ansible.groups = {
	     "webservers" => ["web1","web2"],
	     "dbservers" => ["db1"],
	     "lbservers" => ["lb1"],
	     "all_groups:children" => ["webservers", "dbservers", "lbservers"]
	   	}
	   	ansible.playbook = "site.yml"
	    ansible.extra_vars = { 
        ansible_ssh_user: 'vagrant',
        iface: 'eth1'
       }
	    ansible.limit = 'all'
	  end

  end
end
