# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define 'node' do |node|
    node.vm.box = "ubuntu/xenial64"
    node.hostmanager.enabled = true
    node.hostmanager.manage_host = true
    node.vm.hostname = 'perf01'

    node.vm.provision "shell", path: "provisioning/provision.sh"

    # Ansible
    node.vm.provision :ansible do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.sudo = true
    end

  end
end
