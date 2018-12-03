
Vagrant.configure("2") do |config|
 
  config.vm.box = "ubuntu/xenial64"

  config.vm.provider "virtualbox" do |vbox|
    vbox.memory = 1024
  end

  config.vm.define "web" do |s1|
    s1.vm.network "private_network", ip: "10.0.0.200"
    s1.vm.provision "shell", path: "upgrade_ubuntu.sh"
    s1.vm.provision "shell", path: "install_java8_ubuntu.sh"
  end

  config.vm.define "database" do |s2|
    s2.vm.network "private_network", ip: "10.0.0.201"
    s2.vm.provision "shell", path: "upgrade_ubuntu.sh"
    s2.vm.provision "shell", path: "install_postgresql_ubuntu.sh"
    s2.vm.provision "shell", path: "install_mysql_ubuntu.sh"
  end

end
