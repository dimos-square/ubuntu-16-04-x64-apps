# ubuntu-18-04-x64-apps

## java
```
sudo apt-get update
sudo apt-get install default-jdk
```

## curl
```
sudo apt install curl
```

## rlwrap
```
sudo apt-get install rlwrap
```

## clojure 1.9.0.391
```
curl -O https://download.clojure.org/install/linux-install-1.9.0.391.sh
chmod +x linux-install-1.9.0.391.sh
sudo ./linux-install-1.9.0.391.sh
```

## wget
```
sudo apt-get install wget
```

## leiningen
```
sudo wget -P /usr/local/bin https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein
sudo chmod +x /usr/local/bin/lein
```

## git
```
sudo apt-get update
sudo apt-get install git
```

## docker
```
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce
sudo usermod -a -G docker $USER
```

## docker-compose 1.25.0
```
sudo curl -L https://github.com/docker/compose/releases/download/1.25.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

## terraform 0.11.11
```
sudo wget -P ~/Downloads https://releases.hashicorp.com/terraform/0.11.11/terraform_0.11.11_linux_amd64.zip
sudo unzip ~/Downloads/terraform_0.11.11_linux_amd64.zip -d /usr/local/bin
sudo chmod +x /usr/local/bin/terraform
```

## aws-cli - python 3 - pip

Conda is a package manager for python that, though optional, allows for a better management of environments and I prefer to use it over pip because it's much more flexible. Miniconda is a software bundle that contains python, pip and conda among others, all isolated from the rest of the system.

```
curl -O https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
chmod +x Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh # Say yes to all user prompts
source ~/.bashrc
```

At this point, to verify that all's well, `which pip` and `which python` should both point to the installation directory of miniconda, e.g. `$HOME/miniconda3/bin/pip` and `$HOME/miniconda3/bin/python`
```
pip install awscli
```

## dbeaver
```
wget -O - https://dbeaver.io/debs/dbeaver.gpg.key | sudo apt-key add -
echo "deb https://dbeaver.io/debs/dbeaver-ce /" | sudo tee /etc/apt/sources.list.d/dbeaver.list
sudo apt update && sudo apt install dbeaver-ce
```

## openvpn
```
sudo apt install openvpn easy-rsa
```

## kleopatra
```
sudo apt-get update
sudo apt-get install kleopatra
```

## postman
```
wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz
sudo tar -xzf postman.tar.gz -C /opt
rm postman.tar.gz
sudo ln -s /opt/Postman/Postman /usr/bin/postman
```

## slack
```
sudo snap install slack --classic
```

## toggl 7.4.122
```
wget http://fr.archive.ubuntu.com/ubuntu/pool/main/g/gst-plugins-base0.10/libgstreamer-plugins-base0.10-0_0.10.36-1_amd64.deb
wget http://fr.archive.ubuntu.com/ubuntu/pool/universe/g/gstreamer0.10/libgstreamer0.10-0_0.10.36-1.5ubuntu1_amd64.deb
sudo dpkg -i libgstreamer*.deb
sudo wget -P ~/Downloads https://github.com/toggl/toggldesktop/releases/download/v7.4.122/toggldesktop_7.4.122_amd64.deb
sudo dpkg -i /home/dimos/Downloads/toggldesktop_7.4.122_amd64.deb
sudo apt-get update
sudo apt-get install -f toggldesktop
```

## intellij 2018.3
```
sudo wget -P ~/Downloads https://download.jetbrains.com/idea/ideaIC-2018.3.tar.gz
sudo tar xf ~/Downloads/ideaIC-2018.3.tar.gz -C /opt/
sudo chmod +x /opt/idea-IC-183.4284.148/bin/idea.sh
```
#### plugins
* Leiningen
* cursive
* Markdown support
* HashiCorp Terraform Language support
* Docker integration

### Install IntelliJ via JetBrains Toolbox

An alternative way to install IntelliJ is via Jetbrains Toolbox. This is an official tool by Jetbrains which lets you 
manage (install/update/rollback/remove) Jetbrains IDEs, as well as your projects.

```
wget https://download.jetbrains.com/toolbox/jetbrains-toolbox-1.13.4733.tar.gz
tar --strip-components=1 -xvzf jetbrains-toolbox-1.13.4733.tar.gz
./jetbrains-toolbox && rm jetbrains-toolbox jetbrains-toolbox-1.13.4733.tar.gz
```

## chrome
```
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' | sudo tee /etc/apt/sources.list.d/google-chrome.list
sudo apt-get update
sudo apt-get install google-chrome-stable
```
#### extensions
* LastPass
* AdBlock

## heroku
```
sudo snap install heroku --classic
```
