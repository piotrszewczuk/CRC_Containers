# Vagranfile for CRC Kubernetes Lab

Vagrant.configure("2") do |dockerConfig|
  #VM1: Docker Host 
  dockerConfig.vm.define "docker-host" do |docker|
    docker.vm.box = "opensuse/Leap-15.4.x86_64"
    docker.vm.hostname = "docker-host"
    docker.vm.network :private_network, ip: "192.168.60.20"
    docker.vm.network "forwarded_port", guest:80, host: 80
    docker.vm.network "forwarded_port", guest:443, host: 443
    docker.vm.network "forwarded_port", guest:8888, host: 8888
    docker.ssh.insert_key = false
    docker.vm.provider "virtualbox" do |vDocker|
      vDocker.name = "docker-host"
      vDocker.customize ["modifyvm", :id, "--memory", 4096]
      vDocker.customize ["modifyvm", :id, "--cpus", 2]
      vDocker.customize ["modifyvm", :id, "--groups", "/CRC_Containers"]
    end
    docker.vm.provision "shell", inline: <<-SHELL
    SHELL
  end
end

#Vagrant.configure("2") do |node1Config|
#  #VM2: node1
#  node1Config.vm.define "k8s-node1" do |node1|
#    node1.vm.box = "opensuse/Leap-15.4.x86_64"
#    node1.vm.hostname = "k8s-node1"
#    node1.vm.network "private_network", ip: "192.168.60.10"
#    node1.ssh.insert_key = false
#    node1.vm.provider "virtualbox" do |vNode1|
#      vNode1.name = "k8s-node1"
#      vNode1.customize ["modifyvm", :id, "--memory", 2048]
#      vNode1.customize ["modifyvm", :id, "--cpus", 2]
#      vNode1.customize ["modifyvm", :id, "--groups", "/CRC_Containers"]
#    end
#    node1.vm.provision "shell", inline: <<-SHELL
#      zypper --non-interactive in curl 
#    SHELL
#  end
#end
#
#Vagrant.configure("2") do |node2Config|
#  #VM3: Node2
#  node2Config.vm.define "k8s-node2" do |node2|
#    node2.vm.box = "opensuse/Leap-15.4.x86_64"
#    node2.vm.hostname = "k8s-node2"
#    node2.vm.network :private_network, ip: "192.168.60.12"
#    node2.ssh.insert_key = false
#    node2.vm.provider "virtualbox" do |vNode2|
#      vNode2.name = "k8s-node2"
#      vNode2.customize ["modifyvm", :id, "--memory", 2048]
#      vNode2.customize ["modifyvm", :id, "--cpus", 2]
#      vNode2.customize ["modifyvm", :id, "--groups", "/CRC_Containers"]
#    end
#    node2.vm.provision "shell", inline: <<-SHELL
#      zypper --non-interactive in curl
#    SHELL
#  end
#end
#
#Vagrant.configure("2") do |node3Config|
#  #VM4: Node3
#  node3Config.vm.define "k8s-node3" do |node3|
#    node3.vm.box = "opensuse/Leap-15.4.x86_64"
#    node3.vm.hostname = "k8s-node3"
#    node3.vm.network :private_network, ip: "192.168.60.14"
#    node3.ssh.insert_key = false
#    node3.vm.provider "virtualbox" do |vNode3|
#      vNode3.name = "k8s-node3"
#      vNode3.customize ["modifyvm", :id, "--memory", 2048]
#      vNode3.customize ["modifyvm", :id, "--cpus", 2]
#      vNode3.customize ["modifyvm", :id, "--groups", "/CRC_Containers"]
#    end
#    node3.vm.provision "shell", inline: <<-SHELL
#      zypper --non-interactive in curl
#    SHELL
#  end
#end
