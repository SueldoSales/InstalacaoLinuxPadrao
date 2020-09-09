# Minha instalação Linux padrão
### Testado no Linux KDE Neon


* Instalar alguns pacotes necessários

```shell
sudo apt-get -y install sudo vim vim-scripts unzip zip p7zip-full htop iotop wget lynx curl locate ssh nano build-essential software-properties-common
```

* Instalar e configurar o **Git**

```shell
sudo apt-get install git

git config --global user.name "Sueldo Sales"

git config --global user.email sueldosales@gmail.com
```

* Instalar e configurar o **Apache**

```shell
sudo apt-get install apache2 libapache2-mod-php7.2

sudo vim /etc/apache2/sites-available/000-default.conf

sudo service apache2 reload
```

* Instalar e configurar o **MariaDB**

```shell
sudo apt-get install mariadb-server mariadb-client

sudo systemctl enable mariadb.service
```

* Resolvendo root do **MySQL**

```shell
sudo mysql_secure_installation

sudo mysql -u root

use mysql;

update user set plugin='' where User='root';

flush privileges;

exit;

sudo systemctl restart mariadb.service
```

* Instalar o **PHP** e suas dependências

```shell
sudo apt-get install php7.4 php7.4-mysql php7.4-json php7.4-curl php7.4-gd php7.4-intl php7.4-pspell php7.4-xml php7.4-xmlrpc php7.4-zip php7.4-cli php7.4-ldap aspell graphviz
```

* Instalar e configurar o **PHPMyAdmin**

```shell
sudo apt-get install phpmyadmin

sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf

sudo a2enconf phpmyadmin

systemctl reload apache2
```

* Instalar o **Terminator**

```shell
sudo apt-get install terminator
```

* Instalar e configurar o [**Oh-my-zsh**](https://github.com/robbyrussell/oh-my-zsh)

```shell
sudo apt-get install zsh

sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

chsh -s /bin/zsh
```

* Baixar e instalar o **PIP**

>Link para Download: https://pip.pypa.io/en/stable/installing/

```shell
sudo python get-pip.py
```

* Instalar o [**NVM**](https://github.com/nvm-sh/nvm#installation-and-update)

* Instalar o **VirtualEnv**

```shell
sudo pip install virtualenv
```
* Instalar o **Python3 distutils**

```shell
sudo apt-get install python3-distutils
```

* Instalar o [**Composer**](https://getcomposer.org)

* Instalar o [**Snap**](https://docs.snapcraft.io/installing-snap-on-ubuntu/6740)

```shell
sudo apt install snapd
```

* Instalar o [**Google Chrome**](https://www.google.com.br/chrome/)

* Instalar o [**Code**](https://code.visualstudio.com/Download)
