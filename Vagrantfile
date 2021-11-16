# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.define "cloud1-ubuntu" do |ubuntu|
    ubuntu.vm.hostname = "cloud1-ubuntu"
    ubuntu.vm.box = "generic/ubuntu2004"
    ubuntu.vm.network "forwarded_port", id: "ssh", guest: 22, host: 1345
    ubuntu.vm.network "forwarded_port", guest: 80, host: 1080
    ubuntu.vm.network "forwarded_port", guest: 443, host: 1443
  end

  config.vm.define "cloud1-fedora" do |fedora|
    fedora.vm.hostname = "cloud1-fedora"
    fedora.vm.box = "generic/fedora34"
    fedora.vm.network "forwarded_port", id: "ssh", guest: 22, host: 2345
    fedora.vm.network "forwarded_port", guest: 80, host: 2380
  end

  config.vm.define "cloud1-debian" do |debian|
    debian.vm.hostname = "cloud1-debian"
    debian.vm.box = "debian/buster64"
    debian.vm.network "forwarded_port", id: "ssh", guest: 22, host: 3345
    debian.vm.network "forwarded_port", guest: 80, host: 3380
  end

  config.vm.define "cloud1-alpine" do |alpine|
    alpine.vm.hostname = "cloud1-alpine"
    alpine.vm.box = "generic/alpine314"
    alpine.vm.network "forwarded_port", id: "ssh", guest: 22, host: 4345
    alpine.vm.network "forwarded_port", guest: 80, host: 4380

    alpine.vm.provision "shell",
      inline: "apk update && apk add python2"
  end

end
