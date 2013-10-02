# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|

  config.vm.box        = 'precise64'
  config.vm.box_url    = 'http://files.vagrantup.com/precise64.box'

  config.vm.network :private_network, ip: "192.168.111.222"

  # Port forward Rails
  # config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.provision :ansible do |ansible|
    ansible.inventory_path = 'hosts'
    ansible.sudo           =  true
    ansible.playbook       = 'playbook.yml'
    ansible.verbose        = true
  end
end
