$sshinit = <<SCRIPT
mkdir -m 0700 /root/.ssh
cp /vagrant/files/id_ed25519.pub /root/.ssh/authorized_key
cat /vagrant/files/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
chmod 600 /root/.ssh/authorized_keys
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.define "centos1" do |config|
    config.vm.box = "centos/7"
    config.vm.hostname = "centos1"
    config.vm.provision "shell", inline: $sshinit
  end

  config.vm.define "debian1" do |config|
    config.vm.box = "debian/stretch64"
    config.vm.hostname = "debian1"
    config.vm.provision "shell", inline: $sshinit
  end

  config.vm.define "debian2" do |config|
    config.vm.box = "debian/stretch64"
    config.vm.hostname = "debian2"
    config.vm.provision "shell", inline: $sshinit
  end

  config.vm.define "ubuntu1" do |config|
    config.vm.box = "ubuntu/xenial64"
    config.vm.hostname = "ubuntu1"
    config.vm.provision "shell", inline: $sshinit
  end

end
