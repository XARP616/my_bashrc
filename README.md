# my_bashrc

## Shortcut for python
```alias py=python3```

## Shortcut for docker
```alias dk=docker```
## Shortcut for opening a nautilus window in the current dir
```alias here="nohup nautilus -w . > /dev/null &"```
## After some programming in Windows
```alias cls=clear```
## For opening another console
```alias another="gnome-terminal & disown"```
## Shortcut for checking a specific open ports
```function port() {
  sudo lsof -i:$1
}```
