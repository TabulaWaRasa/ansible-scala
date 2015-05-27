# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant version 1.4.3
# Ansible 1.5

VAGRANTFILE_API_VERSION = "2"
NETWORK_FILE_SYSTEM = false

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

   if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
    config.cache.synced_folder_opts = {
      type: :nfs,
      mount_options: ['rw', 'vers=3', 'tcp', 'nolock']
    }
   end

  config.vm.network :forwarded_port, host: 8000, guest: 8000
  config.vm.network :forwarded_port, host: 8080, guest: 8080
  config.vm.network :private_network, ip: "192.168.111.222"
  config.vm.synced_folder "/home/jaco/Projects/test", "/home/vagrant/test", :nfs => NETWORK_FILE_SYSTEM

  
  config.vm.provision :ansible do |ansible| 
    ansible.limit = 'play_vagrant'
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_path = "provisioning/ansible_hosts"
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 1536
  end

end
