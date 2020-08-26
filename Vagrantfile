IMAGE_NAME = "ubuntu/bionic64"
N = 3

$script = <<-SCRIPT
echo -e "root123\nroot123" | sudo passwd root
sudo apt update
sudo apt install sshpass -y
SCRIPT

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false

    config.vm.provision "shell", inline: $script

    config.vm.provider "virtualbox" do |v|
        v.memory = 512
        v.cpus = 1
    end
      
    (1..N).each do |i|
        config.vm.define "node-#{i}" do |node|
            node.vm.box = IMAGE_NAME
            node.vm.network "private_network", ip: "192.168.99.#{i + 10}"
            node.vm.hostname = "node-#{i}"
        end
    end
end
