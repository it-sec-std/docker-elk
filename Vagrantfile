# A dummy plugin for Barge to set hostname and network correctly at the very first `vagrant up`
module VagrantPlugins
  module GuestLinux
    class Plugin < Vagrant.plugin("2")
      guest_capability("linux", "change_host_name") { Cap::ChangeHostName }
      guest_capability("linux", "configure_networks") { Cap::ConfigureNetworks }
    end
  end
end

Vagrant.configure(2) do |config|
  config.vm.define "elk-exp-field"

#  config.vm.box = "ailispaw/barge"
  config.vm.box = "phusion/ubuntu-14.04-amd64"

  config.vm.synced_folder ".", "/vagrant"

  # for NFS synced folder
  # config.vm.network :private_network, ip: "192.168.33.10"
  # config.vm.synced_folder ".", "/vagrant", type: "nfs",
  #   mount_options: ["nolock", "vers=3", "udp", "noatime", "actimeo=1"]

  # for RSync synced folder
  # config.vm.synced_folder ".", "/vagrant", type: "rsync",
  #   rsync__args: ["--verbose", "--archive", "--delete", "--copy-links"]


  config.vm.provision :docker
  config.vm.provision :docker_compose, yml: "/vagrant/elkx-docker-compose.yml", run: "always"

  config.vm.network :forwarded_port, guest: 5601, host: 5601
end