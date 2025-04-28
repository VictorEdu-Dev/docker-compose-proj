Vagrant.configure("2") do |config|
  
  # Configurações globais
  config.vm.box = "ubuntu/bionic64"

  # Master
  config.vm.define "master" do |master|
    master.vm.hostname = "master"
    master.vm.network "private_network", ip: "192.168.56.10"
    master.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y docker.io
      docker swarm init --advertise-addr 192.168.56.10
    SHELL
  end

  # Node01
  config.vm.define "node01" do |node|
    node.vm.hostname = "node01"
    node.vm.network "private_network", ip: "192.168.56.11"
    node.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y docker.io
      docker swarm join --token SWARM_JOIN_TOKEN 192.168.56.10:2377
    SHELL
  end

  # Node02
  config.vm.define "node02" do |node|
    node.vm.hostname = "node02"
    node.vm.network "private_network", ip: "192.168.56.12"
    node.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y docker.io
      docker swarm join --token SWARM_JOIN_TOKEN 192.168.56.10:2377
    SHELL
  end

  # Node03
  config.vm.define "node03" do |node|
    node.vm.hostname = "node03"
    node.vm.network "private_network", ip: "192.168.56.13"
    node.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y docker.io
      docker swarm join --token SWARM_JOIN_TOKEN 192.168.56.10:2377
    SHELL
  end

end
