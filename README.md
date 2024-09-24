# GOAD-lab-urls
## 5 GOAD Instalación de virtualbox en kali OS
sudo su
###Clonar GOARD
git clone https://github.com/Orange-Cyberdefense/GOAD.git /opt/GOAD
#Actualizar dependencias
apt update
#Cambiar ruta downloads
cd /home/goad/Downloads

###VIRTUALBOX
#vi /etc/apt/sources.list
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] https://download.virtualbox.org/virtualbox/debian bullseye contrib" >> /etc/apt/sources.list
wget -O- https://www.virtualbox.org/download/oracle_vbox_2016.asc | sudo gpg --yes --output /usr/share/keyrings/oracle-virtualbox-2016.gpg --dearmor
wget http://security.debian.org/debian-security/pool/updates/main/o/openssl/libssl1.1_1.1.1n-0+deb10u6_amd64.deb
wget http://http.us.debian.org/debian/pool/main/libv/libvpx/libvpx6_1.9.0-1+deb11u3_amd64.deb

apt update
dpkg -i /home/goad/Downloads/*

apt install virtualbox-7.1
apt install dkms virtualbox-dkms
systemctl stop virtualbox
poweroff
