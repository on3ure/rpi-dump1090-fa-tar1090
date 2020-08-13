# Dump1090 & Tar1090 Raspberry PI 3/4 #

### Why ###
Why not ?

### Install on Linux - Raspberry PI 4 ... Buster Release (2020) ###

## Install Dependancies ##
```console
sudo apt -y update
sudo apt -y full-upgrade
```

## Install dump-10190-fa ##
```console
wget https://flightaware.com/adsb/piaware/files/packages/pool/piaware/p/piaware-support/piaware-repository_3.8.1_all.deb
sudo dpkg -i piaware-repository_3.8.1_all.deb
sudo apt -y update
sudo apt -y install piaware
sudo piaware-config allow-auto-updates yes
sudo piaware-config allow-manual-updates yes
sudo apt -y install dump1090-fa
sudo reboot
```
Go to [flightaware](https://flightaware.com/adsb/piaware/claim to claim your) to claim your station


## Install tar-1090 ##
```console
sudo bash -c "$(wget -nv -O - https://raw.githubusercontent.com/wiedehopf/tar1090/master/install.sh)"
```

## Install automatic gain optimization for dump1090fa ##
```console
sudo bash -c "$(wget -q -O - https://raw.githubusercontent.com/wiedehopf/adsb-scripts/master/dump1090-fa-autogain.sh)"
```

## Disable bluetooth ##
```console
echo "dtoverlay=pi3-disable-bt" | sudo tee -a /boot/config.txt
sudo systemctl disable hciuart
sudo reboot
```

## Console ##
go to http://ip-of-your-pi/tar1090
