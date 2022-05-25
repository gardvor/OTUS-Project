# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.box = "rockylinux/8"
  config.vm.box_version = "4.0.0"

  config.vm.define "firewall" do |firewall|
  firewall.vm.hostname = "firewall"
  firewall.vm.network "private_network", ip: "192.168.10.10"
  firewall.vm.provision "shell", run: "always", path: "ssh_password_on.sh"
end

config.vm.define "nextcloud" do |nextcloud|
  nextcloud.vm.hostname = "nextcloud"
  nextcloud.vm.network "private_network", ip: "192.168.10.20"
  nextcloud.vm.provision "shell", run: "always", path: "ssh_password_on.sh"
end

config.vm.define "db" do |db|
  db.vm.hostname = "db"
  db.vm.network "private_network", ip: "192.168.10.30"
  db.vm.provision "shell", run: "always", path: "ssh_password_on.sh"
end

#config.vm.define "dbreplica" do |dbreplica|
#  dbreplica.vm.hostname = "db"
#  dbreplica.vm.network "private_network", ip: "192.168.10.40"
#  dbreplica.vm.provision "shell", run: "always", path: "ssh_password_on.sh"
#end
#config.vm.define "logserver" do |logserver|
#  logserver.vm.hostname = "logserver"
#  logserver.vm.network "private_network", ip: "192.168.10.50"
#  logserver.vm.provision "shell", run: "always", path: "ssh_password_on.sh"
#end
#config.vm.define "monitoring" do |monitoring|
#  monitoring.vm.hostname = "monitoring"
#  monitoring.vm.network "private_network", ip: "192.168.10.60"
#  monitoring.vm.provision "shell", run: "always", path: "ssh_password_on.sh"
#end
#config.vm.define "backup" do |backup|
#  backup.vm.hostname = "backup"
#  backup.vm.network "private_network", ip: "192.168.10.70"
#  backup.vm.provision "shell", run: "always", path: "ssh_password_on.sh"
#end

  
config.vm.define "ansible" do |ansible|
  ansible.vm.hostname = "ansible"
  ansible.vm.network "private_network", ip: "192.168.10.100"
  ansible.vm.provision "shell", run: "always", path: "ansible_install.sh"
  ansible.vm.provision "shell", run: "always", inline: <<-SHELL
          cp -r /vagrant/ /vagrant-new/    
		      SHELL

end

end