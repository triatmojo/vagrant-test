Vagrant.configure("2") do |config|

  config.vm.define "machine" do |machine|
   machine.vm.box = "ubuntu/trusty64"
   machine.vm.hostname = "machine-server.test"
   machine.vm.network "private_network", ip: "10.70.10.5"
  end


 config.vm.define "web" do |web|
  web.vm.box = "ubuntu/trusty64"
  web.vm.hostname = "webserver.test"
  web.vm.synced_folder "C:Users/ta.sukantono/Documents/test", "/file-web1"
  web.vm.network :private_network, ip: "172.16.20.5"
  web.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2
  SHELL
 end

 
 config.vm.define "db" do |db|
  db.vm.box = "ubuntu/trusty64"
  db.vm.hostname = "database.test"
  db.vm.network "private_network", ip: "172.16.20.55"
  db.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y sqlite
  SHELL
 end

  config.vm.define "app" do |machine|
   machine.vm.box = "generic/ubuntu1804"
   machine.vm.hostname = "app.test"
   machine.vm.network :private_network, ip: "172.16.20.6"
  end

end
