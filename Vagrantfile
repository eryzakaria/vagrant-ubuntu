
Vagrant.configure("2") do |config|

    config.vm.box = "bento/ubuntu-22.04"

    config.vm.provider "virtualbox" do |vb|
      # Display the VirtualBox GUI when booting the machine
      #vb.gui = true
      config.vm.provision "shell", path: "scripts/commen.sh"
    
      # Customize the amount of memory on the VM:
      vb.cpus = 1
      vb.memory = "1024"
      vb.linked_clone = true
    end

    #
    # View the documentation for the provider you are using for more
    # information on available options.
    config.vm.define "ubuntu" do |ubuntu|
        ubuntu.vm.network :private_network, ip: "10.10.10.20"
    end
    # config.vm.define "nginx2" do |nginx2|
    #   nginx2.vm.network :private_network, ip: "10.10.10.21"
    # end
    
    # Enable provisioning with a shell script. Additional provisioners such as
    # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
    # documentation for more information about their specific syntax and use.
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y curl 
    SHELL
  end