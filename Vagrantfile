Vagrant.configure("2") do |config|
    config.vm.define "fw" do |fw|
        fw.vm.box = "bento/ubuntu-24.04"
        fw.vm.network "private_network", ip: "192.168.100.2"
        fw.vm.network "public_network", bridge: "default"
        fw.vm.provision "ansible" do |ansible|
            ansible.playbook = "./playbooks/provision-fw.yaml"
        end
    end

    config.vm.define "client" do |client|
        client.vm.box = "bento/ubuntu-24.04"
        client.vm.network "private_network", ip: "192.168.100.3"
        client.vm.provision "ansible" do |ansible|
            ansible.playbook = "./playbooks/provision-client.yaml"
        end
    end
end
