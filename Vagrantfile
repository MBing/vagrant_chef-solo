# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "AppSaloon64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  # Provision with chef solo
  config.vm.provision :chef_solo do | chef |
    # chef.add_recipe "wordpress"
    chef.add_role("default")
    config.vm.network "forwarded_port", guest: 80, host: 8080
  end

  config.vm.synced_folder "public", "/var/www", :owner => "www-data", :group => "vagrant"

end