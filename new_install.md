# New installation for Ubuntu
## Useful packages
```
sudo apt install curl git
```
## Unsnap, apt firefox
```
sudo add-apt-repository ppa:mozillateam/ppa
sudo snap remove firefox
```
If error:
```
sudo systemctl stop var-snap-firefox-common-host\\x2dhunspell.mount
sudo systemctl disable var-snap-firefox-common-host\\x2dhunspell.mount
```
Install firefox w/ apt
```
sudo apt install firefox
```
Prioritize apt over snap
```
echo 'Unattended-Upgrade::Allowed-Origins:: "LP-PPA-mozillateam:${distro_codename}";' | sudo tee /etc/apt/apt.conf.d/51unattended-upgrades-firefox
```

[Source](https://askubuntu.com/questions/1399383/how-to-install-firefox-as-a-traditional-deb-package-without-snap-in-ubuntu-22)
