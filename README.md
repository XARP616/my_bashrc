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
```bash
function port() {
  sudo lsof -i:$1
}
```

`port 80`
```bash
COMMAND   PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
firefox 23363 leon   95u  IPv4    ...      0t0  TCP  ...
```

## Shortcut for displaying all open ports
```bash
leon@xarp:~$ ports
```

## Measure curl response time
```curltime website.com```

Format file is necessary and included in the repository. Add in the home directory.
[Credits](https://stackoverflow.com/questions/18215389/how-do-i-measure-request-and-response-times-at-once-using-curl#answer-22625150)

## Open a netcat server in a given port
```ncsv <port>```

```ncsv 8002```

## Run any command in the background, silently or showing only error outputs
This is though for opening GUI applications without needing to have have another terminal on the background, such as **`pycharm`** or **`gedit`**.
```bash
silent gedit file.txt test.py
silent pycharm .
```
The function:
* Starts the command in background and routes the output to `/dev/null`
* It is not possible to autocomplete commands after the `silent` keyword, so type it later if so.
* Supports any amount of arguments (`$@`)

## Moving around
This is meant for navigating repeatedly around directories with ease.
* `setloc` will set a checkpoint at the current directory
* `goback` will take us from anywhere to the checkpoint
* `andforth` will take us back from where we issued the `goback` command
* `clearloc` it will clear the location
* `showloc` will display the checkpoint (setloc) and secondary location (goback/andforth) if any
```bash
cd /opt/program
leon@XARP:/opt/program$ setloc
cd ~
leon@XARP:~$ goback
leon@XARP:~$ showloc
Checkpoint location: /tmp
Current location: /tmp
Coming from /home/leon

leon@XARP:/opt/program$ andforth
leon@XARP:~$ clearloc
```

## Calculator
This is an alias for the command `bc` for simple and quick use. 
Do NOT add spaces.
```bash
leon@xarp:~$ calc 2+2
4
```

## Bash reload
Simply reloads `.bashrc` file.

## Empty a file
Simply wipes the contents of a file. Asks for confirmation. ALso checks for file existence.

```bash
leon@xarp:/tmp$ cat a
aaaaaaaa
leon@xarp:/tmp$ empty a
...
leon@xarp:/tmp$ cat a

leon@xarp:/tmp$ empty a
Are you sure you want to clear this file contents? [y/N] n
Cancelled.
leon@xarp:/tmp$ empty a b c
This operation will affect more than one file. Proceed? [y/N] y

leon@xarp:/tmp$ empty
No filename specified

leon@xarp:/tmp$ rm a
leon@xarp:/tmp$ empty a
Are you sure you want to clear this file contents? [y/N] y
File 'a' does not exist
```

## Yes or no?
A function for modularizing decisions in scripts.

```bash
yes_or_no "Are you sure you want to clear this file contents?"
if [ $? -eq 1 ]; then
  echo "yes"
elif [ $? -eq 0]; then
  echo "no"
else
  echo "Not valid input"
fi
```

## Set title
Sets the title of a shell terminal. Does not work for zsh
[Credits](https://unix.stackexchange.com/questions/177572/how-to-rename-terminal-tab-title-in-gnome-terminal)

```bash
set-title my new tab title
```
