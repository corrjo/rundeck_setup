# -*- mode: ruby -*-
# vi: set ft=ruby ts=2 sw=2 :

Vagrant.configure("2") do |config|

	config.ssh.insert_key = false
	config.landrush.enabled = true
	config.landrush.tld = "dev"
	config.vm.network "public_network"
	config.vm.define "rundecktest" do |rundecktest|
		rundecktest.vm.box = "fedora/24-cloud-base"
		rundecktest.vm.hostname = "rundecktest.#{config.landrush.tld}"

		config.vm.provider "virtualbox" do |v|
			v.memory = 4096 
			v.cpus = 2
		end

		if Vagrant.has_plugin?("vagrant-cachier")
			rundecktest.cache.scope = :box
		end

		#Provisionng Config for ansible.
		config.vm.provision "ansible" do |ansible|
			ansible.playbook = "tests/test.yml"
			#run as root
			ansible.sudo = true
		end
	end
end
