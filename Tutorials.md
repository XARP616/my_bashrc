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

## Permissions
### Directory permissions explanation
[Read here](https://unix.stackexchange.com/questions/21251/execute-vs-read-bit-how-do-directory-permissions-in-linux-work#answer-21263)

### Symbolic Link Permissions
[Baeldung - How Do Permissions Apply to Symbolic Links?](https://www.baeldung.com/linux/symlinks-permissions)

## Remote
### Create a banner and a MOTD (Message of the Day)
[Baeldung Tutorial](https://www.baeldung.com/linux/ssh-welcome-message)

## Networking
### Configuring a TCP Wrapper (xinetd)
[How to configure xinetd](https://www.ochobitshacenunbyte.com/2017/01/18/servicios-de-internet-en-linux-con-xinetd/)
[RedHat - TCP Wrappers and xinetd](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-tcp_wrappers_and_xinetd)
[RedHat ES - Archivos de configuración de envolturas TCP](https://access.redhat.com/documentation/es-es/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-tcp_wrappers_and_xinetd-tcp_wrappers_configuration_files)

### Make IPTABLES persistent
[Link to forum](https://unix.stackexchange.com/questions/52376/why-do-iptables-rules-disappear-when-restarting-my-debian-system)

### Logging in IPTABLES
[Link to forum](https://stackoverflow.com/questions/21771684/iptables-log-and-drop-in-one-rule#answer-29544353)

## Docker
### Why there is no `systemctl` in Docker
[Docker forums](https://forums.docker.com/t/systemctl-status-is-not-working-in-my-docker-container/9075)

### Services in Docker
Services can be started manually through the systemd. In Docker we should use the `service` command.
[Read more](https://github.com/MicrosoftDocs/WSL/issues/457#issuecomment-574859373)

#### Start Apache (alt way)
`sudo /etc/init.d/apache2 start`

## Python
### How to handle secrets
Useful when working with secrets such as passwords and tokens. A must not to have passwords hardcoded (even in they are not plaintext, code can be reversed)
[GitGuardian - How to Handle Secrets in Python](https://blog.gitguardian.com/how-to-handle-secrets-in-python/)

## Miscellaneous
### What happens if I have an alias (or function) with the same name as a command
[IBM - command Command](https://www.ibm.com/docs/en/aix/7.2?topic=c-command-command)

### Follow the end of the file (tail)
Perfect for logging

[Read here](https://unix.stackexchange.com/questions/18760/how-does-the-tail-commands-f-parameter-work)

### Where to put binaries
[Read here](https://unix.stackexchange.com/questions/36871/where-should-a-local-executable-be-placed)

### Adjust nano tabspace
[Read here](https://stackoverflow.com/questions/11173769/how-to-make-the-tab-character-4-spaces-instead-of-8-spaces-in-nano)

