 # -*- mode: ruby -*-
# vi: set ft=ruby :


hosts = {
  "elastic01" => "192.168.33.10"
}

Vagrant.configure("2") do |config|
  config.ssh.insert_key = false 
  #config.ssh.private_key_path = File.expand_path('~/.vagrant.d/insecure_private_key')
  config.vm.box = "ubuntu/trusty64"
  #config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  hosts.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.hostname = "%s.example.org" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.memory = 2048
          v.cpus = 1
      end
    end
  end
end
