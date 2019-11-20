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

## toolbox-1.16.6067
```
wget https://download.jetbrains.com/toolbox/jetbrains-toolbox-1.16.6067.tar.gz
tar --strip-components=1 -xvzf jetbrains-toolbox-1.16.6067.tar.gz
./jetbrains-toolbox && rm jetbrains-toolbox jetbrains-toolbox-1.16.6067.tar.gz
```
### IDE
intellij
#### plugins
* Leiningen
* cursive
* Markdown support
* HashiCorp Terraform Language support
* Docker integration

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
* AWS Extend Switch Roles

## heroku
```
sudo snap install heroku --classic
```
