# my_bashrc

## Shortcut for Python3
```alias py=python3```

## For quickly creating Python3 virutal envirnoments
```alias pyenv="python3 -m venv"```

## Shortcut for docker
```alias dk=docker```
## Shortcut for opening a nautilus window in the current dir
```alias here="nohup nautilus -w . > /dev/null &"```
## After some programming in Windows
```alias cls=clear```
## For opening another console
```alias another="gnome-terminal & disown"```

## Shortcut for checking specific open ports
```
function port() {
  sudo lsof -i:$1
}
```

`port 80`
```
COMMAND   PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
firefox 23363 leon   95u  IPv4    ...      0t0  TCP  ...
```

## Measure curl response time
```curltime website.com```

Format file is included in the repository. Add in the home directory.
[Credits](https://stackoverflow.com/questions/18215389/how-do-i-measure-request-and-response-times-at-once-using-curl#answer-22625150)

## Open a netcat server in a given port
```ncsv <port>```

```ncsv 8002```
