#!/bin/bash

#selecting arch
arch=$(dpkg --print-architecture)
#selecting commands
update="apt update -y >/dev/null"
upgrade="apt upgrade -y >/dev/null"
iwget="apt install wget zip unzip figlet -y"
#simple condition sentence
require(){
	eval $update
	eval $upgrade
	eval $iwget
}
echo -e """\033[93m
____▄▀▀▀▄▄▄▄▄▄▄▀▀▀▄_
───█▒▒░░░░░░░░░▒▒█───
────█░░█░░░░░█░░█────
─▄▄──█░░░▀█▀░░░█──▄▄─
█░░█─▀▄░░░░░░░▄▀─█░░█
█▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀█
█-# coded prince dill   █
█#\033[92mW/A:+966595872427  \033[93m█
█  \033[91mngrok installer\033[93m   █
█▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄█
"""
sleep 5
if [ $arch == 'aarch64' ]
then 
echo -e "\033[92m[•] \033[93mInstalling the requirements... "
require
echo -e "\033[92m"
figlet "ngrok"
echo -e "\033[94m"
figlet "for"
echo -e "\033[95m"
figlet $arch
wget "https://bin.equinox.io/a/nmkK3DkqZEB/ngrok-2.2.8-linux-arm64.zip"
unzip "ngrok-2.2.8-linux-arm64.zip"
chmod 777 ngrok
else 
echo -e "\033[92m[•] \033[93mInstalling the requirements... "
require
echo -e "\033[92m"
figlet "ngrok"
echo -e "\033[94m"
figlet "for"
echo -e "\033[95m"
figlet $arch
wget https://github.com/Ahmedmahmed8a/ngrok-arm/raw/master/ngrok-arm
mv ngrok-arm ngrok
chmod 777 ngrok
fi
echo -e """\033[92m 
ngrok has been installed successfully 
YouTube:\033[91mhttps://www.youtube.com/channel/UC4A8Npg7zYgc1LqqHvULKSQ
"""
