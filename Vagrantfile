Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "forwarded_port", guest: 80, host:8089
  config.vm.network "public_network", type: "dhcp"

  config.vm.provision "shell", inline: "
   apt update -y && \
   apt install -y apache2 && \
   apt install -y mysql-server && \
   apt install -y php && \
   apt install -y build-essential dkms && \
   mysql -e create database zabbix
   "
  config.vm.provider "virtualbox" do |v|
  v.memory = 3024
  v.cpus = 6
  v.name = "Aula"

end
end
