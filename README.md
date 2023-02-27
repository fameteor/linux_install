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
`sudo apt-get update`
`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin`

## Create docker group and add your user to a docker group (to use docker commands without `sudo`)
- `sudo groupadd docker`
- `sudo usermod -aG docker francois
- `newgrp docker`

# Install NVM (Node V14) and Meteor (check for the right Node for last Meteor version)
- Install NVM (Node Version Manager) : `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash`
- Install node V14 : `nvm install 14`
- Use node V14 : `nvm use 14`
- Install Meteor : `npm install -g meteor`

# For recording audio :
- `sudo apt-get update`
- `sudo apt-get install flac pavucontrol lame`
- `sudo add-apt-repository ppa:audio-recorder/ppa`
- `sudo apt install audio-recorder`
## Packages :
- `flac` : Free Lossless Audio Codec
- `audio-recorder` : Sound recorder
- `pavucontrol` : PulseAudio VolUme Control
- `lame` : high quality MPEG Audio Layer III (MP3) encoder

# ATOM éditor installation :
- `sudo snap install atom --classic`

# Install to upload Nokia 8110
## Install ADB
- `sudo apt-get install android-tools-adb`
## Gdeploy (https://gitlab.com/suborg/gdeploy)
## Palemoon (or firefox in a fixed version)
- upload palemoon : `palemoon-28.6.1.linux-x86_64.tar.bz2` from : `https://archive.palemoon.org/palemoon/28.x/28.6.1/`
- extract to /opt/palemoon : `tar xvf palemoon-*.tar.bz2 -C /opt/`
- create symlink : `sudo ln -s /opt/palemoon/palemoon /usr/bin/palemoon`
- launch : `palemoon`
