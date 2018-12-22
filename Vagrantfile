Vagrant.configure("2") do |config|

# build the web instance
  config.vm.define "web" do |web|
    web.vm.box = "ubuntu/precise64"
    web.vm.hostname = 'web'
    web.vm.box_url = "ubuntu/precise64"

    web.vm.network :private_network, ip: "192.168.56.101"

    web.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 1024]
      v.customize ["modifyvm", :id, "--name", "web"]
    end
  end

# build the db instance
  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/precise64"
    db.vm.hostname = 'db'
    db.vm.box_url = "ubuntu/precise64"

    db.vm.network :private_network, ip: "192.168.56.102"

    db.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 1024]
      v.customize ["modifyvm", :id, "--name", "db"]
    end
  end
end