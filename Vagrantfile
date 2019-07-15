# -*- mode: ruby -*-
# vi: set ft=ruby :

# Every Vagrant development environment requires a box. You can search for
# boxes at https://atlas.hashicorp.com/search.
# BOX_IMAGE = "ubuntu/trusty32"

Vagrant.configure("2") do |config|
  config.vm.define "staging" do |staging|
    staging.vm.box = "ubuntu/trusty32"
    staging.vm.hostname = "staging"
    staging.vm.network :private_network, ip: "192.168.68.10", auto_correct: true
    staging.vm.network :forwarded_port, guest: 80, host: 8010
    staging.vm.provision :shell, :path => ".provision/bootstrap.sh"
  end

  config.vm.define "prod" do |prod|
    prod.vm.box = "ubuntu/trusty32"
    prod.vm.hostname = "prod"
    prod.vm.network :private_network, ip: "192.168.68.11", auto_correct: true
    prod.vm.network :forwarded_port, guest: 80, host: 8011
    prod.vm.provision :shell, :path => ".provision/bootstrap.sh"
  end

end
