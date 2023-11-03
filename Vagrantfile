Vagrant.configure("2") do |config|
  config.vm.boot_timeout = 600 # Set boot timeout to 10 minutes
  
  config.vm.define "dc1" do |dc1|
    dc1.vm.box = "gusztavvargadr/windows-10"
    dc1.vm.network "private_network", type: "dhcp"
    dc1.vm.network "forwarded_port", guest: 80, host: 8080 # Optional: Forward port 80 on the guest to port 8080 on the host
    dc1.vm.synced_folder ".", "/vagrant", disabled: true
    dc1.vm.synced_folder "/mnt/c/Users/Micheal/lab/vagrant/src/", "/srv/website"
    dc1.vm.provider "virtualbox" do |vb|
      vb.memory = "2048" # Set the amount of memory the VM will use
      vb.cpus = 2 # Set the number of CPUs
    end
  end

  config.vm.define "dc2" do |dc2|
    dc2.vm.box = "gusztavvargadr/windows-10"
    dc2.vm.network "private_network", type: "dhcp"
    dc2.vm.network "forwarded_port", guest: 80, host: 8081 # Optional: Forward port 80 on the guest to port 8081 on the host
    dc2.vm.synced_folder ".", "/vagrant", disabled: true
    dc2.vm.synced_folder "/mnt/c/Users/Micheal/lab/vagrant/src/", "/srv/website"
    dc2.vm.provider "virtualbox" do |vb|
      vb.memory = "2048" # Set the amount of memory the VM will use
      vb.cpus = 2 # Set the number of CPUs
    end
  end
end
