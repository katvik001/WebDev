Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true 
  config.hostmanager.manage_host = true
  config.vm.network "public_network"
  config.vm.provision "shell",
        run: "always",
        inline: "route add default gw 192.168.0.1"

  
### Jenkins VM ###
   config.vm.define "jenkins01" do |jenkins01|
    jenkins01.vm.box = "ubuntu/bionic64"
    jenkins01.vm.hostname = "jenkins01"
	jenkins01.vm.network "private_network", ip: "10.10.10.10"
	jenkins01.vm.provider "virtualbox" do |vb|
		vb.memory = "4096"
   end
   end

   ### Docker VM Prod ###
   config.vm.define "docker01" do |docker01|
	config.vm.synced_folder ".", "/vagrant_data"
    docker01.vm.box = "ubuntu/bionic64"
    docker01.vm.hostname = "docker01" 
	docker01.vm.network "private_network", ip: "10.10.10.20"
    docker01.vm.provider "virtualbox" do |vb|
		vb.memory = "4096"
   end
   end
   
   ### Docker VM Test ###
   config.vm.define "dockerqa" do |dockerqa|
    dockerqa.vm.box = "ubuntu/bionic64"
    dockerqa.vm.hostname = "dockerqa"
	dockerqa.vm.network "private_network", ip: "10.10.10.30"
    dockerqa.vm.provider "virtualbox" do |vb|
            vb.memory = "2048"
   end
   end
	
end

