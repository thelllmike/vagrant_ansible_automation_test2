Vagrant.configure("2") do |config|
  # Set a global boot timeout
  config.vm.boot_timeout = 600

  Define the first VM (dc1)
  config.vm.define "dc1" do |dc1|
    dc1.vm.box = "gusztavvargadr/windows-10"
    dc1.vm.network "private_network", type: "dhcp"
    dc1.vm.network "forwarded_port", guest: 80, host: 8080
    dc1.vm.synced_folder ".", "/vagrant", disabled: true
    dc1.vm.synced_folder "/mnt/c/Users/Micheal/lab/vagrant/src/", "/srv/website"
    dc1.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end

  Define the second VM (dc2)
  config.vm.define "dc2" do |dc2|
    dc2.vm.box = "gusztavvargadr/windows-10"
    dc2.vm.network "private_network", type: "dhcp"
    dc2.vm.network "forwarded_port", guest: 80, host: 8081
    dc2.vm.synced_folder ".", "/vagrant", disabled: true
    dc2.vm.synced_folder "/mnt/c/Users/Micheal/lab/vagrant/src/", "/srv/website"
    dc2.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end

  # Define the third VM (dc3) using the "gusztavvargadr/windows-server" box
  config.vm.define "dc3" do |dc3|
    dc3.vm.box = "gusztavvargadr/windows-server"
    dc3.vm.network "private_network", type: "dhcp"
    # You can configure dc3 similar to dc1 and dc2, with its own network and synced folders.
    # Below are example configurations, adjust as needed.

    # Optionally forward a port if you want to access a service on dc3 from the host machine
    # dc3.vm.network "forwarded_port", guest: 80, host: 8082

    # Synced folder configuration for dc3 if needed
    # dc3.vm.synced_folder "/mnt/c/Users/Micheal/lab/vagrant/src/", "/srv/website"

    # VirtualBox-specific settings for dc3
    dc3.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end
end
