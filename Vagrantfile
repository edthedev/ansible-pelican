# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # config.vm.box = "chef/centos-6.5"
  # config.vm.box = "chef/debian-7.4"
  config.vm.box = "hashicorp/precise32"
# make serve, serves on 8000 by default in Pelican
  config.vm.network :forwarded_port, guest: 8000, host: 8000
  config.vm.synced_folder "blog/", "/blog"

    # v.memory = 4096
    # v.cpus = 2
#  config.vm.provider "virtualbox" do |v|
#    v.gui = true
#  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose = 'vvv'
# For debugging
   # ansible.start_at_task = 'system'
#    ansible.start_at_task = 'latest node'
    #ansible.start_at_task = 'grunt'
  end

end
