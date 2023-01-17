# Bootable USB key creation
- see : https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#3-usb-selection
- download `rufus 3.21`
- download `ubuntu desktop 22.04.1`

# Install Ubuntu 22.01.1 complète sans modifier les partitions

# Hosts file modification
- Add `marais.dev.com` in `etc/hosts` : `127.0.0.1       marais.dev.com`

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

# Install Node and Meteor
- Install NVM (Node Version Manager) : `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash`
- Install node V14 : `nvm install 14`
- Use node V14 : `nvm use 14`
_ Install Meteor : `npm install -g meteor`
