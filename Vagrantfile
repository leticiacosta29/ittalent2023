Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "nginx-001"

  config.vm.network "private_network", ip: "192.168.0.5"
  config.vm.network "public_network"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.synced_folder "./folder-inplace", "./folder-ubuntu"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = "4"
  end

  config.vm.provision "shell", inline: <<-SHELL
      apt-get upgrade -y
      apt-get update -y
      apt-get install -y htop nano python3 nginx
      systemctl start nginx
      systemctl enable nginx
      systemctl status nginx
    SHELL
  end