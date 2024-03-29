# -*- mode: ruby -*-
# vi: set ft=ruby :
# vi: set tabstop=2 :
# vi: set shiftwidth=2 :

Vagrant.configure("2") do |config|

  vms_debian = [
    { :name => "debian-buster", :box => "debian/buster64", :vars => {} },
    { :name => "debian-bullseye", :box => "debian/bullseye64", :vars => {} }
  ]

  conts = [
    { :name => "docker-debian-buster", :docker => "hanxhx/vagrant-ansible:debian10", :vars => {} },
    { :name => "docker-debian-bullseye", :docker => "hanxhx/vagrant-ansible:debian11", :vars => {} },
  ]

  config.vm.network "private_network", type: "dhcp"
  config.vm.synced_folder ".", "/vagrant", id: "vagrant-root", disabled: true

  conts.each do |opts|
    config.vm.define opts[:name] do |m|
      m.vm.provider "docker" do |d|
        d.image = opts[:docker]
        d.remains_running = true
        d.has_ssh = true
      end

      if opts[:name].include? "bullseye"
        m.vm.provision "shell", inline: "[ -f '/root/first_provision' ] || (apt-get update -qq && apt-get -y dist-upgrade && touch /root/first_provision)"
      end

      m.vm.provision "ansible" do |ansible|
        ansible.playbook = "tests/test.yml"
        ansible.verbose = 'vv'
        ansible.become = true
        ansible.extra_vars = opts[:vars].merge({ "nginx_debug_role": true, is_docker: true })
      end
    end
  end

  vms_debian.each do |opts|
    config.vm.define opts[:name] do |m|
      m.vm.box = opts[:box]
      m.vm.provider "virtualbox" do |v|
        v.cpus = 1
        v.memory = 256
      end

      if opts[:name].include? "bullseye"
        m.vm.provision "shell", inline: "[ -f '/root/first_provision' ] || (apt-get update -qq && apt-get -y dist-upgrade && touch /root/first_provision)"
      end

      m.vm.provision "ansible" do |ansible|
        ansible.playbook = "tests/test.yml"
        ansible.verbose = 'vv'
        ansible.become = true
        ansible.extra_vars = opts[:vars].merge({ "nginx_debug_role": true })
      end
    end
  end

end
