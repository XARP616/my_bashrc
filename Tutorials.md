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




## Text processing in bash

* [Text processing in bash - Coreutils in Linux series](https://learnbyexample.github.io/cli_text_processing_coreutils/cat-tac.html)

### Argumentos de programa con getops
Ejemplo de script con getops

[Curl test stress script raw](https://gist.githubusercontent.com/cirocosta/de576304f1432fad5b3a/raw/476eda87ba9666756c6f4010ed43c2aa355c76cf/stress-test.sh)


### Get the name of the file or the directory
[Text processing in bash - basedir and dirnme](https://learnbyexample.github.io/cli_text_processing_coreutils/basename-dirname.html)

### ASCII to numbers in shell
[Bash script to get ASCII values for alphabet](https://unix.stackexchange.com/questions/92447/bash-script-to-get-ascii-values-for-alphabet)

### Multiline in bash: controlling interactive programs, multiline commands, multiline input
[Here Documents](https://tldp.org/LDP/abs/html/here-docs.html)


## Debian
### Create custom `.deb` packages
[MakeUseOf - How to Create DEB Packages for Debian/Ubuntu](https://www.makeuseof.com/create-deb-packages-debian-ubuntu/)

### Fix apt "unsandboxed" issue
[Read here](https://askubuntu.com/questions/908800/what-does-this-apt-error-message-download-is-performed-unsandboxed-as-root)

## SSH
### Create a banner and a MOTD (Message of the Day)
[Baeldung Tutorial](https://www.baeldung.com/linux/ssh-welcome-message)



## Networking

### Configure a VPN server
[Digital Ocean - How To Set Up and Configure an OpenVPN Server](https://www.digitalocean.com/community/tutorials/how-to-set-up-and-configure-an-openvpn-server-on-ubuntu-22-04)

### Configuring a TCP Wrapper (xinetd)
[How to configure xinetd](https://www.ochobitshacenunbyte.com/2017/01/18/servicios-de-internet-en-linux-con-xinetd/)
[RedHat - TCP Wrappers and xinetd](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-tcp_wrappers_and_xinetd)
[RedHat ES - Archivos de configuración de envolturas TCP](https://access.redhat.com/documentation/es-es/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-tcp_wrappers_and_xinetd-tcp_wrappers_configuration_files)

### Make IPTABLES persistent
[Link to forum](https://unix.stackexchange.com/questions/52376/why-do-iptables-rules-disappear-when-restarting-my-debian-system)

### Logging in IPTABLES
[Link to forum](https://stackoverflow.com/questions/21771684/iptables-log-and-drop-in-one-rule#answer-29544353)

### Local reverse proxy for resolving domains with ports
[Baelding - Mapping Hostnames with Ports in `/etc/hosts`](https://www.baeldung.com/linux/mapping-hostnames-ports)


## Docker
### Why there is no `systemctl` in Docker
[Docker forums](https://forums.docker.com/t/systemctl-status-is-not-working-in-my-docker-container/9075)

### Services in Docker
Services can be started manually through the systemd. In Docker we should use the `service` command.
[Read more](https://github.com/MicrosoftDocs/WSL/issues/457#issuecomment-574859373)

#### Start Apache (the other way)
`sudo /etc/init.d/apache2 start`



## Vagrant
### Fix apt manual install "unsanboxed" error 
[P](https://github.com/fgrehm/vagrant-cachier/issues/175#issuecomment-292630871)



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

### Run commands through SSH
Multiline commands
```bash
ssh -T $_remote <<'EOL'
	now="$(date)"
	name="$HOSTNAME"
	up="$(uptime)"
	echo "Server name is $name"
	echo "Server date and time is $now"
	echo "Server uptime: $up"
	echo "Bye"
EOL
```
[How to run commands in SSH](https://www.cyberciti.biz/faq/unix-linux-execute-command-using-ssh/)

### Execute function with timeout
[Shell function with timeout](https://stackoverflow.com/questions/9954794/execute-a-shell-function-with-timeout)

### Linux show certificate information
[How to Check a Certificate with OpenSSL Commands in Linux?](https://www.ssldragon.com/blog/check-certificate-openssl-linux/#View-the-Full-Certificate-Details)

### Handling signals in bash
[Handling signals in bash](https://www.baeldung.com/linux/bash-signal-handling)

### Sort disk usage `du` by size
[Sort du by size](https://serverfault.com/questions/62411/how-can-i-sort-du-h-output-by-size)

### Update alternatives
[Read here](https://www.baeldung.com/linux/update-alternatives-command)
