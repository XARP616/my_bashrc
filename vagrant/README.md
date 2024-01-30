# Vagrant
Here some Vagrant files

## Gitlab Ubuntu Runner
A basic Ubuntu Jammy (22) setup for a Gitlab runner. It can be easily modified to work with other Linux distros (only need to change the base image).
As long as it is Linux, should be okay.

The commands set up the runner service. It will be necessary to follow the remaining commands (setting up the token and so on, specified when creating the runner) to make it work.

## Vuls
This will be a local installation of Vuls. You can take it as reference, or use it as a script (take the provision section).
Vuls will work also under other distros, since the Vagrantfile will perform the whole compilation process. Nonetheless, to minimize the vulnerability database fetch time, only 
the Ubuntu data is get. Should change it if working with other Linux distributions.
