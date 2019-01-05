# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|

  config.vm.box = "centos/7"

  config.puppet_install.validate_version = false

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false
    # Customize the amount of memory on the VM:
    vb.memory = "512"
  end

  (1..2).each do |i|
    config.vm.define "gw#{i}" do |node|
      node.vm.hostname = "gw#{i}.local"
      node.vm.network "private_network", ip: "192.168.#{i}00.1",
        virtualbox__intnet: "gw#{i}_lan"
    end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/site.yml"
    #ansible.raw_arguments = ["-vvv"]
    ansible.groups = {
      "gateways" => ['gw*']
    }
  end

end
