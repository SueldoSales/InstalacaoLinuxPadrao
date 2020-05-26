# Minha instalação Linux padrão
### Testado no Linux Mint


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

* Instalar e configurar o **MySQL**

```shell
sudo apt-get install mysql-server
```

* Resolvendo root do **MySQL**

```shell
sudo /etc/init.d/mysql stop

sudo mysqld --skip-grant-tables --user=mysql &

sudo /etc/init.d/mysql restart

sudo mysql

FLUSH PRIVILEGES;

ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_passowrd';

quit;

sudo mysql -u root -p

SELECT user,plugin,host FROM mysql.user WHERE user = 'root';

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'enter_password_here';

FLUSH PRIVILEGES;

```

* Instalar o **PHP** e suas dependências

```shell
sudo apt-get install php7.2 php7.2-mysql php7.2-json php7.2-curl php7.2-gd php7.2-intl php7.2-pspell php7.2-xml php7.2-xmlrpc php7.2-zip php7.2-cli php7.2-ldap aspell graphviz
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

* Instalar o [**NodeEnv**](https://github.com/ekalinin/nodeenv)

```shell
sudo pip install nodeenv
```

* Instalar o [**Yarn**](https://yarnpkg.com/pt-BR/)

```shell
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt-get install --no-install-recommends yarn
```

* Instalar o **VirtualEnv**

```shell
sudo pip install virtualenv
```
* Instalar o **Python3 distutils**

```shell
sudo apt-get install python3-distutils
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
