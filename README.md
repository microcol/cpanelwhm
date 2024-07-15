# cpanelwhm
Cpanel Install script
1- Detected Server Or VPS 
2- 2 static ip
3- Domain 
4- NS1 & NS2 
5- Whm/cpanel 
6- Whmcs
7- Ecommerce website
8- Paypal Account Or any payment Getway

#################  STAGE - 1 ###############################
### Change Server Root User Passwd
sudo passwd root
sudo su - root 
nano /etc/ssh/sshd_config 
### PermitRootLogin yes
sudo systemctl restart ssh.service
### try login with root user 
sudo apt update && sudo apt -y upgrade -y && sudo reboot

#################  STAGE - 2 - Cpanel Install ###############################
1- hostnamectl set-hostname cloudone.Roterhosting.lan
2- cd /home && curl -o latest -L https://securedownloads.cpanel.net/latest && sh latest

#################  STAGE - 3 - Cpanel Config ###############################
3- License 
4- Config
custom_begin_smtp_predata 

TXT _dmarc = v=DMARC1; p=quarantine; pct=100
TXT _domainkey = t=y; o=~;

#################  STAGE - 4 - Install softaculous & jetbackup5 ###############################
wget -N https://files.softaculous.com/install.sh
chmod 755 install.sh
./install.sh 


bash <(curl -LSs http://repo.jetlicense.com/static/install)
jetapps --install jetbackup5-cpanel stable


