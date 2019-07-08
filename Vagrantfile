Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.define "mng01" do |server|
    server.vm.network "private_network", ip: "172.12.33.10"
    server.vm.provision :ansible do |ansible|
      ansible.extra_vars = {
        git_install_version: "2.21.0"
      }
      ansible.playbook = "playbook.yml"
      ansible.limit = "all"
    end
  end

  config.vm.define "web01" do |server|
    server.vm.network "private_network", ip: "172.12.33.11"
  end

end
