Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/23.04"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = "1"
#    vb.net = ""
#    vb.forwarded_port = ""
  end
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    uname -sr > ~/first_kernel_version
    sudo apt-get update
    sudo apt-get upgrade
    cd /tmp
    wget https://kernel.ubuntu.com/mainline/v6.4/amd64/linux-headers-6.4.0-060400-generic_6.4.0-060400.202306271339_amd64.deb
    wget https://kernel.ubuntu.com/mainline/v6.4/amd64/linux-headers-6.4.0-060400_6.4.0-060400.202306271339_all.deb
    wget https://kernel.ubuntu.com/mainline/v6.4/amd64/linux-image-unsigned-6.4.0-060400-generic_6.4.0-060400.202306271339_amd64.deb
    wget https://kernel.ubuntu.com/mainline/v6.4/amd64/linux-modules-6.4.0-060400-generic_6.4.0-060400.202306271339_amd64.deb
    sudo dpkg -i *.deb
    sudo update-grub
    sudo reboot now
#    uname -sr > ~/final_kernel_version
#    sudo apt-get check
#    cat ~/first_kernel_version
#    cat ~/final_kernel_version
  SHELL
#  config.vm.synced_folder ".", "/vagrant"
end
