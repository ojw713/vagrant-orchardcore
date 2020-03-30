# Create a minimal Ubuntu box
Vagrant.require_version ">= 2.1.2"
Vagrant.configure(2) do |config|

    # Configure the base box
    config.vm.define "ubuntu" do |ubuntu|

        # Find the latest images on https://app.vagrantup.com/ubuntu
        ubuntu.vm.box = "ubuntu/bionic64"
        # ubuntu.disksize.size = "25GB"

        ubuntu.vm.hostname = "orchardcore"

        ubuntu.vm.network :forwarded_port, guest: 80, host: 8077

        ubuntu.vm.synced_folder "orchardcore/", "/orchardcore/"
    end


    # Configure the VirtualBox parameters
    config.vm.provider "virtualbox" do |vb|
        vb.name = "orchardcore"
        vb.customize [ "modifyvm", :id, "--memory", "3072" ]
    end

   # Configure Time Sync on vagrantup to avoid time drift
   require 'time'
   offset = ((Time.zone_offset(Time.now.zone) / 60) / 60)
   timezone_suffix = offset >= 0 ? "-#{offset.to_s}" : "+#{offset.to_s}"
   timezone = 'Etc/GMT' + timezone_suffix
   config.vm.provision :shell, :inline => "sudo rm /etc/localtime && sudo ln -s /usr/share/zoneinfo/" + timezone + " /etc/localtime", run: "always"

    # Configure the box with Ansible
    config.vm.provision "ansible_local" do |ansible|
        ansible.compatibility_mode = "2.0"
        ansible.playbook = "/orchardcore/0_install.yml"
    end

    # Reload the box with reload plugin
    # config.vm.provision :reload

end
