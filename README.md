# test
Just for my practice

# Init Ubuntu
``` bash
sudo vi /etc/sudoers
```
``` shell
#includedir /etc/sudoers.d
max     ALL=(ALL) NOPASSWD: ALL
```

# Grub
/etc/default/grub
```
GRUB_DEFAULT=saved
GRUB_SAVEDEFAULT="true"
```
sudo update-grub


# Chrome
```
sudo apt install curl
curl https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
sudo apt-get update
sudo apt-get --no-install-recommends install -y google-chrome-stable
```

# OTX
```
sudo apt-get install python3-dev
pip uninstall mmcv
pip install mmcv-full
```
