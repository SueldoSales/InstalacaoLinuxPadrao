# Minha instalação Linux padrão

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
sudo apt-get install apache2 libapache2-mod-php7.4

sudo vim /etc/apache2/sites-available/000-default.conf

sudo service apache2 reload
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

* Instalar o [**NVM**](https://github.com/nvm-sh/nvm#installation-and-update)

* Habilitar o **Yarn**

```shell
corepack enable
```

* Instalar o [**Google Chrome**](https://www.google.com/intl/pt-BR/chrome/)

* Instalar o [**Code**](https://code.visualstudio.com/download)

* Instalar o [**Local**](https://localwp.com/)

* Instalar [**ZSH com OhMyZsh**](https://github.com/ohmyzsh/ohmyzsh/wiki)

* Instalar a fonte [**Cascadia Code**](https://github.com/microsoft/cascadia-code)
