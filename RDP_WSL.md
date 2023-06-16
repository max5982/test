# How To Enable WSL2 Ubuntu GUI and use RDP to Remote

* Update for lastest one
```
sudo apt update && sudo apt -y upgrade
```

* Install a GUI distro to Ubuntu
```
sudo apt install -y ubuntu-desktop
sudo apt install -y xfce4
#sudo apt-get install -y xfce4 xfce4-goodies
#sudo apt-get install -y kubuntu-desktop
```
Half way through the installation you will be prompt for this configurating sddm, select lightdm

* Install and configure XDRP, and change the RDP port to 3392
```
sudo apt-get install xrdp
sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
sudo sed -i 's/3389/3392/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
sudo ufw allow from any to any port 3392 proto tcp
```

* Open and Edit the location file
```
sudo vi /etc/xrdp/startwm.sh

-test -x /etc/X11/Xsession && exec /etc/X11/Xsession
-exec /bin/sh /etc/X11/Xsession
+# test -x /etc/X11/Xsession && exec /etc/X11/Xsession
+# exec /bin/sh /etc/X11/Xsession
+# xce4
+startxfce4
```
  

*  Enable dbus
```
#enable dbus
sudo systemctl enable dbus
sudo /etc/init.d/dbus start
sudo /etc/init.d/xrdp start
# check xrdp status
sudo /etc/init.d/xrdp status
```

# Launch your Winodws Remote Desktop Connection, or mstsc
localhost:3392
