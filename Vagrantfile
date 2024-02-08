Vagrant.configure("2") do |config|
  # config.vm.box = "bento/ubuntu-20.04" # ubuntu 20.04
  config.vm.box = "ubuntu/bionic64" # ubuntu 18

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end

  config.vm.define "my_host" do |m|
    m.vm.network "private_network", ip: "192.168.61.0"
  end
end
