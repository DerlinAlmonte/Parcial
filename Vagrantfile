Vagrant.configure("2") do |config|
  # Configuración para la primera máquina virtual
  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/focal64"
    web1.vm.network "private_network", ip: "192.168.33.10"
    web1.vm.synced_folder "./html", "/var/www/html"
    web1.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo ufw allow 'Apache Full'
      sudo systemctl enable apache2
      sudo systemctl start apache2
    SHELL
  end

  # Configuración para la segunda máquina virtual
  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/focal64"
    web2.vm.network "private_network", ip: "192.168.33.11"
    web2.vm.synced_folder "./html", "/var/www/html"
    web2.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo ufw allow 'Apache Full'
      sudo systemctl enable apache2
      sudo systemctl start apache2
    SHELL
  end
end