Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.synced_folder "./data", "/data"
  config.ssh.forward_x11 = true
  config.vm.provision "shell", inline: <<-SHELL
    curl -sL https://deb.nodesource.com/setup_6.x -o nodesource_setup.sh
    sudo bash nodesource_setup.sh
    sudo apt-get install nodejs -y
    sudo apt-get install build-essential -y
 SHELL
end
