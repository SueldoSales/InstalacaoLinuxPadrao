# Minha instalação Linux padrão


* Instalar alguns pacotes necessárias

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
sudo apt-get install apache2 libapache2-mod-php7.X

sudo vim /etc/apache2/sites-available/000-default.conf

sudo service apache2 reload
```

* Instalar e configurar o **MySQL**

```shell
sudo apt-get install mysql-server
```

* Instalar o **PHP** e suas dependências

```shell
sudo apt-get install php7.X php7.X-mysql php7.X-json php7.X-curl php7.X-gd php7.X-intl php7.X-pspell php7.X-xml php7.X-xmlrpc php7.X-zip php7.X-cli php7.X-ldap aspell graphviz
```

* Instalar e configurar o **PHPMyAdmin**

```shell
sudo apt-get install phpmyadmin

sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf

sudo a2enconf phpmyadmin

sudo service apache2 reload
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

* Instalar o [**NodeEnv**](https://github.com/ekalinin/nodeenv)

```shell
sudo pip install nodeenv
```
* Instalar o [**Composer**](https://getcomposer.org)

```shell
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '93b54496392c062774670ac18b134c3b3a95e5a5e5c8f1a9f115f203b75bf9a129d5daa8ba6a13e2cc8a1da0806388a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```
```shell
sudo mv composer.phar /usr/local/bin/composer
```
* Instalar o [**Snap**](https://docs.snapcraft.io/installing-snap-on-ubuntu/6740)

```shell
sudo apt install snapd
```

* Instalar o **Google Chrome**

>Link para download: https://www.google.com.br/chrome/browser/desktop/

* Instalar o **Atom**

>Link para download: https://atom.io/

* Instalar o **Code**

>Link para download: https://code.visualstudio.com/Download

* Instalar o [**Spotify**](https://www.spotify.com/br/download/linux/)

```shell
snap install spotify
```
