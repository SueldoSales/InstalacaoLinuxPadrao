# Minha instalação Linux padrão

* Instalar alguns pacotes necessários

```shell
sudo apt -y install vim vim-scripts unzip zip p7zip-full htop iotop wget lynx curl locate ssh nano build-essential software-properties-common
```

* Instalar e configurar o **Git**

```shell
sudo apt install git

git config --global user.name "Nome Sobrenome"

git config --global user.email seuemail@mail.com
```
* Instalar [**ZSH com OhMyZsh**](https://github.com/ohmyzsh/ohmyzsh/wiki)

* Instalar e configurar o **Apache**

```shell
sudo apt install apache2 libapache2-mod-php

sudo vim /etc/apache2/sites-available/000-default.conf

sudo service apache2 reload
```

* Instalar o **PHP** e suas dependências

```shell
sudo apt install php php-mysql php-json php-curl php-gd php-intl php-pspell php-xml php-xmlrpc php-zip php-cli php-ldap aspell graphviz
```

* Instalar e configurar o **PHPMyAdmin**

```shell
sudo apt install phpmyadmin

sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf

sudo a2enconf phpmyadmin

systemctl reload apache2
```

* Instalar o [**NVM**](https://github.com/nvm-sh/nvm#installation-and-update)

* Instalar o **Yarn**

```shell
npm install --global yarn

yarn --version
```

* Instalar o [**Google Chrome**](https://www.google.com/intl/pt-BR/chrome/)

* Instalar o [**Code**](https://code.visualstudio.com/download)

* Instalar o [**Local**](https://localwp.com/)

* Instalar a fonte [**Cascadia Code**](https://github.com/microsoft/cascadia-code)
