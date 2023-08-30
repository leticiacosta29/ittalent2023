Vagrant.configure("2") do |config|
  config.vm.define "default" do |vm|
  config.vm.provider :libvirt do |libvirt|
    # Define a imagem do sistema operacional
    vm.vm.box = "ubuntu/bionic64" # Imagem Ubuntu 20.04

    # Define a quantidade de RAM
    vm.vm.provider "virtualbox" do |vb|
      vb.memory = "2048" # 2 GB de RAM
    end

    # Encaminhamento de portas (exemplo: encaminha a porta 8080 do host para a porta 80 da VM)
    vm.vm.network "forwarded_port", guest: 80, host: 8080
	# Sincronização de pastas entre a máquina local e a máquina virtual
    config.vm.synced_folder "C:/Users/allreles/Documents/Vagrant/ittalents_t", "/home/vagrant/ittalents"
  end
end