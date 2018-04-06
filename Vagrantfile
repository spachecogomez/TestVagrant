# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "instance1" do |instance1|
    instance1.vm.box = "ubuntu/xenial64"
    instance1.vm.network "private_network", ip: "192.168.50.3"
    instance1.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2 apache2-bin apache2-data apache2-utils
    cp /vagrant/index.html /var/www/
    echo 'Instance1' >> /var/www/index.html 
    SHELL
end

config.vm.define "instance2" do |instance2|
    instance2.vm.box = "ubuntu/xenial64"
    instance2.vm.network "private_network", ip: "192.168.50.4"
    instance2.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2 apache2-bin apache2-data apache2-utils
    cp /vagrant/index.html /var/www/
    echo 'Instance2' >> /var/www/index.html 
    SHELL
end

config.vm.define "instance3" do |instance3|
    instance3.vm.box = "ubuntu/xenial64"
    instance3.vm.network "private_network", ip: "192.168.50.5"
    instance3.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2 apache2-bin apache2-data apache2-utils
    cp /vagrant/index.html /var/www/
    echo 'Instance3' >> /var/www/index.html 
    SHELL
end

config.vm.define "balancer" do |balancer|
    balancer.vm.box = "ubuntu/xenial64"
    balancer.vm.network "private_network", ip: "192.168.50.6"
    balancer.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2 apache2-bin apache2-data apache2-utils
    sudo a2enmod proxy
    cp /vagrant/000-default.conf /etc/apache2/sites-enabled/
    sudo service apache2 stop
    sudo service apache2 start
    SHELL
end

end
