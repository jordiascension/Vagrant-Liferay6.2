# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  #config.vm.box = "hashicorp/precise64"
  config.vm.box = "ubuntu/trusty64"

   
  config.vm.define "liferay7" do |liferay7|
  end

  config.vm.hostname = "liferay7"

  #config.vm.provider :virtualbox do |vb, override|

  #end

  config.vm.provider "virtualbox" do |v|
        v.memory = 3072
        v.cpus = 2
    end

  config.vm.network :forwarded_port, guest: 8080, host: 4040

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file = "base.pp"
    puppet.module_path = "modules"
  end

end
