# 🐧 Minha Instalação Linux Padrão

Este guia documenta todos os passos necessários para configurar um ambiente de desenvolvimento completo após uma nova instalação do Linux Ubuntu/Debian.

## 📋 Índice

- [Pré-requisitos](#-pré-requisitos)
- [Pacotes Essenciais do Sistema](#-pacotes-essenciais-do-sistema)
- [Configuração do Git](#-configuração-do-git)
- [Terminal e Shell](#-terminal-e-shell)
- [Ambiente de Desenvolvimento Web](#-ambiente-de-desenvolvimento-web)
  - [Apache](#apache)
  - [PHP](#php)
  - [PHPMyAdmin](#phpmyadmin)
- [Node.js e Ferramentas JavaScript](#-nodejs-e-ferramentas-javascript)
- [Aplicações e Editores](#-aplicações-e-editores)
- [Fontes e Personalização](#-fontes-e-personalização)
- [Script de Instalação Automatizada](#-script-de-instalação-automatizada)
- [Verificações Pós-Instalação](#-verificações-pós-instalação)
- [Troubleshooting](#-troubleshooting)

## 🔧 Pré-requisitos

Antes de começar, certifique-se de que:

- Você tem privilégios de sudo
- O sistema está atualizado
- Você tem conexão com a internet

```shell
# Atualizar o sistema
sudo apt update && sudo apt upgrade -y

# Verificar versão do sistema
lsb_release -a
```

## 📦 Pacotes Essenciais do Sistema

Instalar ferramentas básicas necessárias para desenvolvimento e administração do sistema:

```shell
sudo apt -y install \
  vim vim-scripts \
  unzip zip p7zip-full \
  htop iotop \
  wget lynx curl \
  locate \
  ssh \
  nano \
  build-essential \
  software-properties-common \
  apt-transport-https \
  ca-certificates \
  gnupg \
  lsb-release
```

**Verificação:**

```shell
# Testar algumas ferramentas instaladas
htop --version
curl --version
```

## 🔐 Configuração do Git

Instalar e configurar o Git para controle de versão:

```shell
# Instalar Git
sudo apt install git

# Configurar usuário (substitua pelos seus dados)
git config --global user.name "Seu Nome Completo"
git config --global user.email "seu.email@exemplo.com"

# Configurações adicionais recomendadas (opcional)
git config --global init.defaultBranch main
git config --global core.editor vim
git config --global pull.rebase false
```

**Verificação:**

```shell
git --version
git config --list
```

## 🖥️ Terminal e Shell

### ZSH com Oh My Zsh

Instalar e configurar um terminal mais poderoso e customizável:

```shell
# Instalar ZSH
sudo apt install zsh

# Instalar Oh My Zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Definir ZSH como shell padrão
chsh -s $(which zsh)
```

**Plugins recomendados** (editar `~/.zshrc`):

```shell
plugins=(git node npm yarn docker docker-compose)
```

**Verificação:**

```shell
echo $SHELL
zsh --version
```

## 🌐 Ambiente de Desenvolvimento Web

### Apache

```shell
# Instalar Apache e módulo PHP
sudo apt install apache2 libapache2-mod-php

# Habilitar módulos úteis
sudo a2enmod rewrite
sudo a2enmod ssl

# Configurar site padrão (opcional)
sudo vim /etc/apache2/sites-available/000-default.conf

# Reiniciar Apache
sudo systemctl restart apache2
sudo systemctl enable apache2
```

**Verificação:**

```shell
sudo systemctl status apache2
curl -I localhost
```

### PHP

```shell
# Instalar PHP e extensões essenciais
sudo apt install php php-mysql php-json php-curl php-gd php-intl \
  php-pspell php-xml php-xmlrpc php-zip php-cli php-ldap php-mbstring \
  php-bcmath php-soap aspell graphviz

# Configurar PHP (opcional)
sudo vim /etc/php/*/apache2/php.ini
```

**Verificação:**

```shell
php --version
php -m | grep -E "(mysql|curl|gd)"
```

### PHPMyAdmin

```shell
# Instalar PHPMyAdmin
sudo apt install phpmyadmin

# Configurar Apache para PHPMyAdmin
sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf
sudo a2enconf phpmyadmin

# Reiniciar Apache
sudo systemctl reload apache2
```

**Verificação:**

```shell
curl -I localhost/phpmyadmin
```

## 🟢 Node.js e Ferramentas JavaScript

### NVM (Node Version Manager)

```shell
# Instalar NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash

# Recarregar o shell ou executar:
source ~/.bashrc
# ou se usando zsh:
source ~/.zshrc

# Instalar a versão LTS mais recente do Node.js
nvm install --lts
nvm use --lts
nvm alias default node
```

### Yarn

```shell
# Habilitar Corepack (vem com Node.js 16+)
corepack enable

# Ou instalar globalmente
npm install -g yarn
```

**Verificação:**

```shell
node --version
npm --version
yarn --version
```

## 🛠️ Aplicações e Editores

### Google Chrome

```shell
# Baixar e instalar Google Chrome
wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" | sudo tee /etc/apt/sources.list.d/google-chrome.list
sudo apt update
sudo apt install google-chrome-stable
```

### Visual Studio Code

```shell
# Adicionar repositório oficial da Microsoft
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
sudo apt update
sudo apt install code
```

### Local (LocalWP)

```shell
# Baixar da página oficial: https://localwp.com/
# Ou usar wget (verificar versão mais recente)
wget https://cdn.localwp.com/releases-stable/6.7.0+6387/local-6.7.0-linux.deb
sudo dpkg -i local-*.deb
sudo apt-get install -f  # Corrigir dependências se necessário
```

**Verificação:**

```shell
google-chrome --version
code --version
```

## 🔤 Fontes e Personalização

### Cascadia Code

```shell
# Criar diretório para fontes
mkdir -p ~/.local/share/fonts

# Baixar Cascadia Code
wget -O cascadia-code.zip https://github.com/microsoft/cascadia-code/releases/latest/download/CascadiaCode.zip

# Extrair e instalar
unzip cascadia-code.zip -d cascadia-code
cp cascadia-code/ttf/*.ttf ~/.local/share/fonts/

# Atualizar cache de fontes
fc-cache -fv

# Limpar arquivos temporários
rm -rf cascadia-code cascadia-code.zip
```

**Verificação:**

```shell
fc-list | grep -i cascadia
```

## 🚀 Script de Instalação Automatizada

Para facilitar futuras instalações, você pode criar um script automatizado:

```shell
#!/bin/bash
# Criar arquivo install-dev-environment.sh
cat > install-dev-environment.sh << 'EOF'
#!/bin/bash

echo "🐧 Iniciando instalação do ambiente de desenvolvimento..."

# Atualizar sistema
sudo apt update && sudo apt upgrade -y

# Pacotes essenciais
sudo apt -y install vim vim-scripts unzip zip p7zip-full htop iotop wget lynx curl locate ssh nano build-essential software-properties-common apt-transport-https ca-certificates gnupg lsb-release

# Git
sudo apt install git -y

# ZSH
sudo apt install zsh -y

# Apache e PHP
sudo apt install apache2 libapache2-mod-php php php-mysql php-json php-curl php-gd php-intl php-pspell php-xml php-xmlrpc php-zip php-cli php-ldap php-mbstring php-bcmath php-soap aspell graphviz -y

# PHPMyAdmin
sudo apt install phpmyadmin -y

echo "✅ Instalação básica concluída!"
echo "📝 Lembre-se de configurar manualmente:"
echo "   - Git (user.name e user.email)"
echo "   - Oh My Zsh"
echo "   - NVM"
echo "   - Google Chrome"
echo "   - VS Code"
echo "   - Local"
echo "   - Cascadia Code"
EOF

chmod +x install-dev-environment.sh
```

## ✅ Verificações Pós-Instalação

Execute estes comandos para verificar se tudo foi instalado corretamente:

```shell
# Verificar serviços
sudo systemctl status apache2
sudo systemctl status mysql  # Se MySQL foi instalado

# Verificar versões
git --version
php --version
node --version
npm --version
yarn --version

# Verificar acessos web
curl -I localhost
curl -I localhost/phpmyadmin
```

## 🔧 Troubleshooting

### Problemas Comuns

**Apache não inicia:**

```shell
sudo systemctl status apache2
sudo journalctl -u apache2
sudo apache2ctl configtest
```

**PHPMyAdmin não acessível:**

```shell
sudo a2enconf phpmyadmin
sudo systemctl reload apache2
```

**NVM command not found:**

```shell
source ~/.bashrc
# ou
source ~/.zshrc
```

**Permissões do Apache:**

```shell
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
```

### Logs Úteis

- Apache: `/var/log/apache2/error.log`
- PHP: `/var/log/apache2/error.log` ou `/var/log/php*.log`
- Sistema: `journalctl -f`

---

## 📚 Recursos Adicionais

- [Oh My Zsh Documentation](https://github.com/ohmyzsh/ohmyzsh/wiki)
- [NVM Repository](https://github.com/nvm-sh/nvm)
- [PHP Configuration](https://www.php.net/manual/en/configuration.php)
- [Apache Documentation](https://httpd.apache.org/docs/)

---

**Última atualização:** $(date +"%d/%m/%Y")

> 💡 **Dica:** Mantenha este documento atualizado conforme suas necessidades evoluem!
