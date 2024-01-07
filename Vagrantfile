# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration.
  config.vm.box = "generic/rhel9"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 8196
    # v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    v.linked_clone = true
  end

  # Application server 1.
  config.vm.define "podman1" do |app|
    app.vm.hostname = "podman1"
    app.vm.network :private_network, ip: "192.168.56.10"
  end

end

