Vagrant.configure("2") do |config|
  # Configuração da máquina Master (Manager)
  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/bionic64"
    master.vm.hostname = "master"
    master.vm.network "private_network", ip: "192.168.56.10"
    master.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"  
    end
    master.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y docker.io
      docker swarm init --advertise-addr 192.168.56.10
    SHELL
  end

  # Configuração do Node 01 (Worker)
  config.vm.define "node01" do |node01|
    node01.vm.box = "ubuntu/bionic64"
    node01.vm.hostname = "node01"
    node01.vm.network "private_network", ip: "192.168.56.11"
    node01.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  
    end
    node01.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y docker.io
      docker swarm join --token <TOKEN INDIVIDUAL> 192.168.56.10:2377
    SHELL
  end

  # Configuração do Node 02 (Worker)
  config.vm.define "node02" do |node02|
    node02.vm.box = "ubuntu/bionic64"
    node02.vm.hostname = "node02"
    node02.vm.network "private_network", ip: "192.168.56.12"
    node02.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  
    end
    node02.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y docker.io
      docker swarm join --token <TOKEN INDIVIDUAL> 192.168.56.10:2377
    SHELL
  end

  # Configuração do Node 03 (Worker)
  config.vm.define "node03" do |node03|
    node03.vm.box = "ubuntu/bionic64"
    node03.vm.hostname = "node03"
    node03.vm.network "private_network", ip: "192.168.56.13"
    node03.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  
    end
    node03.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y docker.io
      docker swarm join --token <TOKEN INDIVIDUAL> 192.168.56.10:2377
    SHELL
  end
end
