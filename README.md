
## 5 GOAD Instalación de virtualbox en kali OS
- sudo su
- git clone https://github.com/Orange-Cyberdefense/GOAD.git /opt/GOAD
- apt update
- cd /home/goad/Downloads
- echo "deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] https://download.virtualbox.org/virtualbox/debian bullseye contrib" >> /etc/apt/sources.list
- wget -O- https://www.virtualbox.org/download/oracle_vbox_2016.asc | sudo gpg --yes --output /usr/share/keyrings/oracle-virtualbox-2016.gpg --dearmor
- wget http://security.debian.org/debian-security/pool/updates/main/o/openssl/libssl1.1_1.1.1n-0+deb10u6_amd64.deb
- wget http://http.us.debian.org/debian/pool/main/libv/libvpx/libvpx6_1.9.0-1+deb11u3_amd64.deb
- apt update
- dpkg -i /home/goad/Downloads/*
- apt install virtualbox-7.1
- apt install dkms virtualbox-dkms
- systemctl stop virtualbox
- poweroff

## 7 GOAD Instalación de requerimientos para instalar el laboratorio GOAD
- apt install vagrant
- apt install pipx 
- pipx install ansible
- pipx install ansible-core==2.12.6  
- cp /root/.local/share/pipx/venvs/ansible/bin/ansible /usr/local/bin/ansible                                                                                                                                                                                    
- cp /root/.local/share/pipx/venvs/ansible/bin/ansible /usr/local/lib/python3.12/dist-packages/ansible
- cp /root/.local/share/pipx/venvs/ansible/bin/ansible-galaxy  /usr/bin/ansible-galaxy                                                                                                                  
- cp /root/.local/share/pipx/venvs/ansible/bin/ansible-galaxy  /usr/local/bin/ansible-galaxy                                                                                                                      
- cp /root/.local/share/pipx/venvs/ansible/bin/ansible-galaxy  /usr/share/bash-completion/completions/_ansible-galaxy
- gem install winrm winrm-fs winrm-elevated
- vagrant plugin install vagrant-vbguest
- vagrant plugin install vagrant-reload
- pip install ansible-core==2.12.6 --break-system-packages
- pip install pywinrm --break-system-packages
- apt install ansible-core
- cd /opt/GOAD
- /root/.local/share/pipx/venvs/ansible/bin/ansible-galaxy install -r ansible/requirements.yml 
- ./goad.sh -t check -l GOAD -p virtualbox -m local
