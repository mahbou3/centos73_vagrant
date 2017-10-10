Vagrant.configure("2") do |config|

  config.vm.box = "CentOS73"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "centos73"
    vb.cpus = 1
    vb.memory = 1024
  end

  config.vm.define 'centos73' do |machine|
    machine.vm.hostname = "centos73"
    machine.vm.network "public_network"

    machine.vm.provision :ansible_local do |ansible|
      ansible.playbook       = "centos73_vagrant_main.yml"
      ansible.verbose        = "vvv"
      ansible.install        = true
      ansible.raw_arguments  = ["--diff"]
    end
  end

end