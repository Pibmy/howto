

```bash
apt-get update && apt-get upgrade

# FROM task-lxde-desktop PACKAGE
apt-get install --no-install-recommends task-xfce-desktop
apt-get install --no-install-recommends gnome-orca

# FROM lxde PACKAGE
apt-get install dbus-session-bus network-manager-gnome xfce4-goodies xfce4-power-manager xfce4-terminal
# (optional)
apt-get install tango-icon-theme

# Basic apps (navigator, txt editor)
apt-get install firefox-esr mousepad 

# ADD ADMIN MODE
apt-get install sudo
gpasswd -a user sudo

# VBOX ADDITIONS
apt-get install build-essential module-assistant
m-a prepare
sudo mount /dev/cdrom /media/cdrom.
sh /media/cdrom/VBoxLinuxAdditions.run
gpasswd -a user vboxsf

# TOOLS
sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common

# ADD SSH KEYS


# PYTHON Virtual Envs
sudo apt-get install python3-venv


# GIT
apt-get install git
# ADD GIT CONFIG FILES (.gitignore, .gitconfig, .gitattributes)


# DOCKER / DOCKER-COMPOSE
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io

# --- docker-compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose



# VISUALCODE

curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'

sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install code

# Microsoft ODBC driver (require root / no sudo)

curl https://packages.microsoft.com/config/debian/9/prod.list > /etc/apt/sources.list.d/mssql-release.list
sudo apt-get update
# Is required ??
# sudo ACCEPT_EULA=Y apt-get install msodbcsql17
sudo apt-get install unixodbc-dev
```