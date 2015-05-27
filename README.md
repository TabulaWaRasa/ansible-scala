#Basic Scala Vagrant Box setup with Ansible Playbook

##Includes
  - Oracle Java 8
  - Scala

##Requirements
- VirtualBox https://www.virtualbox.org/wiki/Downloads 
- Vagrant http://www.vagrantup.com/downloads.html 
- Ansible http://docs.ansible.com/ 

          $ sudo apt-get install software-properties-common
          $ sudo apt-add-repository ppa:ansible/ansible
          $ sudo apt-get update
          $ sudo apt-get install ansible

- Linux NFS Daemon

          sudo apt-get install nfs-kernel-server

- Vagrant-Cachier Plugin:
 
          vagrant plugin install vagrant-cachier

