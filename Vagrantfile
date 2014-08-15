# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure("2") do |config|
  # Defines the Vagrant box name, download URL, IP and hostname
  config.vm.define :vagrant do |vagrant|
    vagrant.vm.box = "hashicorp/precise64"
    vagrant.vm.hostname = "legacy"
  end

  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Add more memory
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", 2048]
  end

  config.vm.provision :shell, :inline => "sh /vagrant/provision.sh;"

end