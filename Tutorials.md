# "Tutorials" section
Online sources for doing specific things in Linux

## Managing processes
### Reataching terminals: deatached, foreground and background processes
* fg, bg, disown, nohup
* %1, %2
* Reatach processes

Read article:

[Baeldung - Attach a Terminal to a Detached Process in Linux](https://www.baeldung.com/linux/attach-terminal-detached-process)

### Exit siganls when TTY ends
* [In depth look](https://unix.stackexchange.com/questions/318369/what-happens-to-background-jobs-after-exiting-the-shell)
* [How to set such behavior](https://stackoverflow.com/questions/4298741/how-bash-handles-the-jobs-when-logout)
* [Why some process do not terminate](https://superuser.com/questions/662431/what-exactly-determines-if-a-backgrounded-job-is-killed-when-the-shell-is-exited)

Conclusions: although TTY may send SIGHUP control singal, the program may choose to ignore it. Some processes are worthier as a service.

### Traps + signal codes
[TutorialsPoint - Signals and Traps](https://www.tutorialspoint.com/unix/unix-signals-traps.htm)

## Managing services
### Add a program or script as a service
* Very complete tutorial: [Baeldung - Creating User’s Services With systemd](https://www.baeldung.com/linux/systemd-create-user-services)
* Good tips for configuring the service: [Link](https://medium.com/@benmorel/creating-a-linux-service-with-systemd-611b5c8b91d6)

[Link to forum](https://unix.stackexchange.com/questions/236084/how-do-i-create-a-service-for-a-shell-script-so-i-can-start-and-stop-it-like-a-d)

## Miscellaneous
### What happens if I have an alias (or function) with the same name as a command
[IBM - command Command](https://www.ibm.com/docs/en/aix/7.2?topic=c-command-command)

### Follow the end of the file (tail)
Perfect for logging

[Read here](https://unix.stackexchange.com/questions/18760/how-does-the-tail-commands-f-parameter-work)

### Where to put binaries
[Read here](https://unix.stackexchange.com/questions/36871/where-should-a-local-executable-be-placed)
