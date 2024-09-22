Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"  # Ubuntu 20.04 (libvirt-compatible box)

  config.vm.provider "libvirt" do |v|
    v.memory = 1024
    v.cpus = 2  # Optional: Specify CPU count if needed
  end

  config.vm.define "my_host" do |m|
    m.vm.network "private_network", ip: "192.168.61.0"
  end
end
