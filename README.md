# my_bashrc

## Shortcut for Python3
```alias py=python3```

## For quickly creating Python3 virutal envirnoments
alias pyenv="python3 -m venv"

## Shortcut for docker
```alias dk=docker```
## Shortcut for opening a nautilus window in the current dir
```alias here="nohup nautilus -w . > /dev/null &"```
## After some programming in Windows
```alias cls=clear```
## For opening another console
```alias another="gnome-terminal & disown"```

function port() {
  sudo lsof -i:$1
}
## Shortcut for checking a specific open ports
```
function port() {
  sudo lsof -i:$1
}```
