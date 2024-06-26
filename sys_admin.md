# System administrator section
This section is meant to be a compilation of useful Sysadmin commands.

## Services
The two main commands for managing services are `service` and `systemctl`. The main difference over both is the capabilities, where `systemctl` 
is a much more powerful command. Nonetheless, there are some underlying differences that may depend also in specificities of each distro.

* [Forum brief explanation](https://serverfault.com/questions/867322/what-is-the-difference-between-service-and-systemctl)
* [More in depth article](https://www.makeuseof.com/service-vs-systemctl-in-linux/)

### `systemctl`
What systemctl actually manages are "**units**" (where services are a subtype of such). These simply are objects that `systemd` knows how to manage. 
Here we do not pretend to delve deeper into this. Instead, we are going to focus into **service management**.

#### List processes
By default, the command outputs all *units* that have been loaded. Does the same that `systemctl list-units`
* `--type=service` -> Shows only the services
* `--state=running` -> Allows to filter by the status of the service (`running` can be replaced by any of the below states)
  * `active`
    * `running`
    * `failed`
    * `exited`
  * `inactive`
    * `dead`
  * More about states [here](https://www.computernetworkingnotes.com/linux-tutorials/systemd-units-explained-with-types-and-states.html)

* All unit types can be found [here](https://www.digitalocean.com/community/tutorials/understanding-systemd-units-and-unit-files#types-of-units).
* All status types can be found [here](https://www.computernetworkingnotes.com/linux-tutorials/systemd-units-explained-with-types-and-states.html).

#### Service management
* `enable` -> adds a service to system startup
* `disable` -> removes a service from startup
* `start` -> starts a service at the moment
* `stop` -> halts a service
* `status` -> checks the status of a service (running, stopped...)

#### Sources
* [Digital Ocean - How To Use Systemctl to Manage Systemd Services and Units](https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units) (Accessed: 02-oct-2023)
* [Digital Ocean - Understanding Systemd Units and Unit Files](https://www.digitalocean.com/community/tutorials/understanding-systemd-units-and-unit-files) (Accessed: 02-oct-2023)

### `service` 
The services that this command manages are managed by **System V**.
* `--status-all` -> will output the status of all processes
  * `[ + ]` means service is running
  * `[ - ]` means service exited
  * `[ ? ]` means that the service does not have status
* `--full-restart` -> restarts all running

Source: program *man* page

### `pstree`
Will display a tree with processes and subprocesses.

* Specifying a user will allow us to show only their processes. For example, `pstree $USER` will show only yours. `pstree` is the same as `pstree root`
* It is also possible to display the PID of each process `pstree -p`

### `journalctl`
When processes fail, the command `systemctl status` may not deliver as much information as we need. For this kind of situation, we can check the *ctl journal*.

* `journalctl` will output all logs from `systemctl`.
* `journalctl -e` will show only the last entries of the log.
* `jounralctl -u NAME.service` (replacing `NAME`) will allow us to filter by service (for example, `docker.service`) and debug why it failed to start/run (whatever).

## System information
Commands for retrieving information about the system

### `uname`
Prints system info
* `-a` all avaliable entries
* `--help` to see all options (kernel, os, so on)

### `uptime`
Shows uptime of the system.
* `--pretty`, hours and minutes of uptime
* `--since`, date since system is running

### `lsb_release`
Shows distribution-specific information.
* `lsb_release -a` shows all information. Most recommended.
* `lsb_release -h` to get specific information of the release.

### `dmesg`
To examine or control the kernel ring buffer. Useful to get the latest system logs.

## System resources

### `ulimit`
Shows the system limits for the different resources (memory, disk, cpu...)
* `ulimit -a` shows all system limits.
* `ulimit -<flag> <value>` to edit a value (the flag is shown with `-a`)

* [Mongodb docs](https://www.mongodb.com/docs/manual/reference/ulimit/)

## User information

### User activity
* `last` latest logins
* `lastlog` shows the latest login for every user
* `who` shows what users have an open session
* `w` shows who is connected and WHAT is doing

### User logins
* `faillog -u %USER` shows failed logins
* `passwd -l user` locks the (password of) a specific account
* `passwod -u user` to revert

## Filesystem

### Watch over changes in the filesystem
```bash
auditctl -w /etc/passwd -p war -k password-file
```
[Read here](https://www.cyberciti.biz/tips/linux-audit-files-to-see-who-made-changes-to-a-file.html)

## Remote execution

### Nagios NRPE
* [Documentation (explanation + installation intructions)](https://assets.nagios.com/downloads/nagioscore/docs/nrpe/NRPE.pdf)
* [Nagios Plugins archive](http://nagios-plugins.org/download/)
* [NRPE (check nrpe) archive](https://github.com/NagiosEnterprises/nrpe/releases/tag/nrpe-4.1.0)
* [Tutorial instalación y configuración](https://www.busindre.com/instalar_nrpe_para_monitorizar_con_nagios)
* [Otro caso con NSClient++](https://www.bujarra.com/nagios-monitorizando-nrpe/)
## Remote access
* Fail2ban utility (to mitigate automated scripts trying to brute force logins)
* `sshfs` (ssh filesystem) to mount a remote filesystem

