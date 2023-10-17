Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
  end

  # Open up 8080 for jenkins
  config.vm.network "forwarded_port", guest: 8080, host: 8080

  # Run ansible installation on first boot 
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "install-jenkins.yml"
  end
end

