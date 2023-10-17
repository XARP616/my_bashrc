# New installation for Ubuntu
## Useful packages
```bash
sudo apt install curl git progress bpytop screen

# OhMyZsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
### Progress of processes
`progress -w`
[Read here](https://unix.stackexchange.com/questions/705022/how-to-show-progress-when-checking-checksums-using-sha256sum)

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
