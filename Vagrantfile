# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

# Installation script
$script = <<SCRIPT
echo Provisioning system ...
apt-get update
apt-get install -y nodejs
apt-get install -y npm
apt-get install -y git
npm install -g abapmerge
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "bento/opensuse-leap-42.3"
  config.vm.provision "shell", inline: $script
	config.vm.synced_folder "data","/home/vagrant/data/", mount_options: ["dmode=775,fmode=777"]
end
