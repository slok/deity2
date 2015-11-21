# Vagrantfile

VAGRANTFILE_API_VERSION = "2"

box = 'ubuntu/trusty64'
hostname = 'ci'
ip_prefix = '192.168.99.10'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.ssh.insert_key = false
  config.ssh.forward_agent = true

  (0..2).each do |i|
    config.vm.define "ci#{i}" do |ci|
      ci.vm.box = box
      ci.vm.host_name = hostname + i.to_s
      ci.vm.network :private_network, ip: ip_prefix + i.to_s
      ci.vm.provider "virtualbox" do |v|
        v.memory = 512
        v.cpus = 1
      end
    end
  end
end
