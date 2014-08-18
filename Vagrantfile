# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "hashicorp/precise64"

  # Apache port forwardings
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provision "docker" do |d|
    # Building Docker images
    d.build_image "/vagrant",
      args: "-t frobini/apachecy"

    # Run Docker images
    d.run "frobini/apachecy",
      args: "-d -p '80:80'"
  end

end