# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define('netradio') do |node|
    node.vm.box = "ubuntu/wily64"
    node.vm.box_check_update = true

    # node.vm.network "forwarded_port", guest: 80, host: 8080
    # node.vm.network "private_network", ip: "192.168.33.10"
    # node.vm.network "public_network"

    # node.vm.synced_folder "../data", "/vagrant_data"

    node.vm.provider "virtualbox" do |vb|
      #vb.gui = true
      vb.memory = "1024"
    end

    node.vm.provision "ansible" do |ansible|
      ansible.playbook = 'server.yml'
      ansible.groups = {
        'server' => ['netradio']
      }
    end
  end
end
