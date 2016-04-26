# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  #
  # hygieia-dev
  #
  config.vm.define "hygieia", :primary => true do |hygieia|
    hygieia.vm.box = "liatrio/hygieia-petclinic-demo-baked"
    #hygieia.vm.box = "hygieia-petclinic-demo-baked"
    #config.vm.box_url = "../hygieia-petclinic-demo-baked.box"

    hygieia.vm.hostname = 'hygieia'
    hygieia.vm.network :private_network, ip: "192.168.100.10"
    hygieia.vm.network :forwarded_port, guest: 22, host: 2210, id: "ssh"
    hygieia.vm.network :forwarded_port, guest: 3000, host: 13000 # hygieia
    hygieia.vm.network :forwarded_port, guest: 8080, host: 18080 # hygieia-api

    hygieia.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--cpus", 2]
      v.customize ["modifyvm", :id, "--memory", 1024]
      #v.customize ["modifyvm", :id, "--name", "hygieia-liatrio"]
    end

    hygieia.vm.provision "shell", inline: "firewall-cmd --permanent --add-port=3000/tcp --add-port=8080/tcp && firewall-cmd --reload"

  end

end
