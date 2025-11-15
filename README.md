# Bootable USB key creation
- see : https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#3-usb-selection
- download `rufus 3.21`
- download `ubuntu desktop 22.04.1`

# Install Ubuntu 24.04.02 sans effacer les données de la partition home
- booter sur la clé USB (sur DELL 7480, appuyer plein de fois sur F12 au démarrage jusqu'à avoir le menu "one shot boot"
- suivre l'assistant d'install jusqu'à "rechercher une version plus récence de l'utilitaire d'install", faire ok, l'arrêter et le relancer
- choisir "installation complète" et choisir manuellement les partitions pour réinstaller et formater que la partition système /. Monter le /home sur la bonne partition

# Install Ubuntu 22.01.1 complète sans modifier les partitions

# Hosts file modification
- Add `marais.dev.com` in `etc/hosts` : `127.0.0.1       marais.dev.com`

# Installer les logiciels complémentaires
- Docker et Docker-compose
``sudo apt-get update
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
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin``

## Create docker group and add your user to a docker group (to use docker commands without `sudo`)
- `sudo groupadd docker`
- `sudo usermod -aG docker francois`
- `newgrp docker`

# Install NVM (Node V14) and Meteor (check for the right Node for last Meteor version)
- Install NVM (Node Version Manager) : `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash`
- Install node V14 : `nvm install 14`
- Use node V14 : `nvm use 14`
- Install Meteor : `npm install -g meteor`

# Meteor 3
- desinstall previous meteor : `npm uninstall -g meteor`
- delete `~/.meteor`
- reinstall meteor : `curl https://install.meteor.com/ | sh`

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

# Install to upload Nokia 8110
## Install ADB
- `sudo apt-get install android-tools-adb`
## Gdeploy (https://gitlab.com/suborg/gdeploy)
## Palemoon (or firefox in a fixed version)
- upload palemoon : `palemoon-28.6.1.linux-x86_64.tar.bz2` from : `https://archive.palemoon.org/palemoon/28.x/28.6.1/`
- extract to /opt/palemoon : `sudo tar xvf palemoon-*.tar.bz2 -C /opt/`
- create symlink : `sudo ln -s /opt/palemoon/palemoon /usr/bin/palemoon`
- launch : `palemoon`

# canon MG3550 installation
## printer and scanner (works with Ubuntu scan utility)
- upload Canon MG3500 series IJ Printer Driver Ver. 4.00 for Linux (debian Packagearchive) : `cnijfilter-mg3500series-4.00-1-deb.tar.gz`
- in the upload directory : `tar xvzf cnijfilter-mg3500series-4.00-1-deb.tar.gz`
- `cd cnijfilter-mg3500series-4.00-1-deb`
- `bash install.sh`

# canon MG2250 installation
## printer and scanner (works with Ubuntu scan utility)
- upload Canon MG2200 series IJ Printer Driver Ver. 3.80 for Linux (debian Packagearchive) : `cnijfilter-mg2200series-3.80-1-deb.tar.gz`
- in the upload directory : `tar xvzf cnijfilter-mg2200series-3.80-1-deb.tar.gz`
- `cd cnijfilter-mg2200series-3.80-1-deb`
- `bash install.sh`

# Ubuntu software installation
- installer `vlc`, `gimp` et `ìnkscape`

# Wireshark installation
- `sudo add-apt-repository ppa:wireshark-dev/stable`
- `sudo apt-get update`
- `sudo apt-get install wireshark`
- `sudo wireshark`

# Kdenlive installation (video editor)
- `sudo apt update`
- `sudo apt install kdenlive`

# Java versions management
- install JAVA 17 : `sudo apt install openjdk-17-jdk openjdk-17-jre`
- To get the list of installed versions : `update-java-alternatives --list`
- To know which version is running : `java --version`
- To switch to a specific version : `sudo update-java-alternatives --set java-1.17.0-openjdk-amd64`

# Route converter (GPX éditor and maps)
- download : `https://www.routeconverter.com/downloads/`
- run : `java -jar RouteConverterLinux.jar`

# Passage en Ubuntu 24.04

# Réinstall ATOM
- Télécharger `atom-amd64.deb` sur le github éditeur : `https://github.com/atom/atom/releases`
- `sudo dpkg -i atom-amd64.deb`
