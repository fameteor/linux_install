# Bootable USB key creation
- see : https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#3-usb-selection
- download `rufus 3.21`
- download `ubuntu desktop 22.04.1`

# Install Ubuntu 22.01.1 complète sans modifier les partitions

# Installer les logiciels complémentaires
- Docker et Docker-compose
`sudo apt-get update`
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
