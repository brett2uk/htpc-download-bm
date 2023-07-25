$script = <<-SCRIPT
apt-get update
apt-get install git docker docker-compose -y
systemctl enable docker && systemctl start docker
chown -R vagrant:vagrant /media
git clone https://github.com/brett2uk/htpc-download-bm.git
chown -R vagrant:vagrant htpc-download-box
cd htpc-download-box
cp .env.example .env
docker-compose up -d
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.provision "shell", inline: $script
  config.vm.synced_folder "C:\Users\btfm\Downloads\media", "/media"
end
