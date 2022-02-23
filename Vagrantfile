# To run on windows: https://www.vagrantup.com/docs/other/wsl
# Plugin to run on WSL2: https://github.com/Karandash8/virtualbox_WSL2

# export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"

# run this command. Project fould should be under /mnt/c:
# export VAGRANT_WSL_WINDOWS_ACCESS_USER_HOME_PATH="/mnt/c/"

# Solve ssh problem:
# cp .vagrant/machines/wordpress/virtualbox/private_key ~
#  chmod 600 ~/private_key
# ansible wordpress -u vagrant --private-key ~/private_key -i hosts -m shell -a 'echo Hello, World'

Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/trusty64"

    config.vm.provider "virtualbox" do |v|
        v.memory = 1024
    end

    config.vm.define "wordpress" do |m|
        m.vm.network "private_network", ip: "192.168.56.10"
    end

    config.vm.define "mysql" do |m|
        m.vm.network "private_network", ip: "192.168.56.20"
    end

end
