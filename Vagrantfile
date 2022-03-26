IMAGE_NAME = "generic/fedora28"
N = 2

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false

    config.vm.provider "virtualbox" do |v|
        v.memory = 1800
        v.cpus = 2
    end
      
    config.vm.define "k8s-master" do |master|
        master.vm.box = IMAGE_NAME
        master.vm.network "private_network", ip: "172.16.1.50"
        master.vm.hostname = "k8s-master"
         
            
    end

    (1..N).each do |i|
        config.vm.define "node-#{i}" do |node|
            node.vm.box = IMAGE_NAME
            node.vm.network "private_network", ip: "172.16.1.#{i + 50}"
            node.vm.hostname = "node-#{i}"
            
        end
    end
end
