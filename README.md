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
sudo apt-get install apache2 libapache2-mod-php7.0

sudo vim /etc/apache2/sites-available/000-default.conf

sudo service apache2 reload
```

* Instalar e configurar o **MySQL**

```shell
sudo apt-get install mysql-server
```

* Instalar o **PHP** e suas dependências

```shell
sudo apt-get install php7.0 php7.0-mysql php7.0-json php7.0-curl php7.0-gd php7.0-intl php7.0-pspell php7.0-xml php7.0-xmlrpc php7.0-zip php7.0-cli php7.0-ldap aspell graphviz
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

sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-

zsh/master/tools/install.sh -O -)"

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

* Instalar o **Google Chrome**

>Link para Download: https://www.google.com.br/chrome/browser/desktop/

* Instalar o **Atom**

>Link para Download: https://atom.io/

* Instalar o [**Spotify**](https://www.spotify.com/br/download/linux/)

```shell
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 0DF731E45CE24F27EEEB1450EFDC8610341D9410

echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list

sudo apt-get update

sudo apt-get install spotify-client
```
