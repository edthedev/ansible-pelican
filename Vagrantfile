# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # config.vm.box = "chef/centos-6.5"
  # config.vm.box = "chef/debian-7.4"
  config.vm.box = "hashicorp/precise32"
  config.vm.network :forwarded_port, guest: 80, host: 8080
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
