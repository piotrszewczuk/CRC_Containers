# Vagranfile for CRC Kubernetes Lab

Vagrant.configure("2") do |dockerConfig|
  #VM1: Docker Host 
  dockerConfig.vm.define "docker-host" do |docker|
    docker.vm.box = "almalinux/8"
    docker.vm.hostname = "docker-host"
    docker.vm.network :private_network, ip: "192.168.60.20"
    docker.vm.network "forwarded_port", guest:80, host: 80
    docker.vm.network "forwarded_port", guest:443, host: 443
    docker.vm.network "forwarded_port", guest:8080, host: 8080
    docker.vm.network "forwarded_port", guest:8888, host: 8888
    docker.ssh.insert_key = false
    docker.vm.provider "virtualbox" do |vDocker|
      vDocker.name = "docker-host"
      vDocker.customize ["modifyvm", :id, "--memory", 4096]
      vDocker.customize ["modifyvm", :id, "--cpus", 2]
      vDocker.customize ["modifyvm", :id, "--groups", "/CRC_Containers"]
    end
    docker.vm.provision "shell", inline: <<-SHELL
      dnf install -y dnf-utils
      dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
      dnf update -y
      dnf install -y docker-ce
      systemctl enable --now docker
    SHELL
  end
end

Vagrant.configure("2") do |masterConfig|
  #VM2: master
  masterConfig.vm.define "k3s-master" do |master|
    master.vm.box = "opensuse/Leap-15.3.x86_64"
    master.vm.hostname = "k3s-master"
    master.vm.network "private_network", ip: "192.168.60.10"
    master.vm.network "forwarded_port", guest:6443, host: 6443
    master.ssh.insert_key = false
    master.vm.provider "virtualbox" do |vMaster|
      vMaster.name = "k3s-master"
      vMaster.customize ["modifyvm", :id, "--memory", 2048]
      vMaster.customize ["modifyvm", :id, "--cpus", 1]
      vMaster.customize ["modifyvm", :id, "--groups", "/CRC_Containers"]
    end
    master.vm.provision "shell", inline: <<-SHELL
      zypper --non-interactive in curl mc
    SHELL
  end
end

Vagrant.configure("2") do |node1Config|
  #VM3: Node1
  node1Config.vm.define "k3s-node1" do |node1|
    node1.vm.box = "opensuse/Leap-15.3.x86_64"
    node1.vm.hostname = "k3s-node1"
    node1.vm.network :private_network, ip: "192.168.60.12"
    node1.ssh.insert_key = false
    node1.vm.provider "virtualbox" do |vNode1|
      vNode1.name = "k3s-node1"
      vNode1.customize ["modifyvm", :id, "--memory", 2048]
      vNode1.customize ["modifyvm", :id, "--cpus", 1]
      vNode1.customize ["modifyvm", :id, "--groups", "/CRC_Containers"]
    end
    node1.vm.provision "shell", inline: <<-SHELL
      zypper --non-interactive in curl
    SHELL
  end
end

Vagrant.configure("2") do |node2Config|
  #VM4: Node2
  node2Config.vm.define "k3s-node2" do |node2|
    node2.vm.box = "opensuse/Leap-15.3.x86_64"
    node2.vm.hostname = "k3s-node2"
    node2.vm.network :private_network, ip: "192.168.60.14"
    node2.ssh.insert_key = false
    node2.vm.provider "virtualbox" do |vNode2|
      vNode2.name = "k3s-node2"
      vNode2.customize ["modifyvm", :id, "--memory", 2048]
      vNode2.customize ["modifyvm", :id, "--cpus", 1]
      vNode2.customize ["modifyvm", :id, "--groups", "/CRC_Containers"]
    end
    node2.vm.provision "shell", inline: <<-SHELL
      zypper --non-interactive in curl
    SHELL
  end
end

