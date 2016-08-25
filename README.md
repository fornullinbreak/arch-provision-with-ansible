# arch-provision-with-ansible
Arch linux installation provisioned with Ansible, for use with thinkpad x61, later for more general use

## WARNING

Ansible role is reseting layout of your /dev/sda drive,__YOU WILL LOSE YOUR DATA__,  make sure you look what playbook is doing and test it on virtual mashine first!!

## What the script is doing ?
Performs fresh installation of Arch linux. For now please look into playbooks.

TODO: add more details

## Precondidtions
1. You created Arch installation medium
1. Machine is booted into installation ( machine on which you want to install and provision Arch linux, from now called BOX_A )
1. BOX_A got IP configured, and you can reach your provision machine ( called BOX_P )
1. BOX_A: root password is set ( passwd root )
1. BOX_A: Sshd is started ( systemctl start sshd )
1. BOX_P: ssh key is copied to BOX_A  ( on BOX_P: ssh-copy-id root@<IP_OF_BOX_A> )
1. BOX_P: update hosts file in ansible playbook to match your BOX_A

Now you should be good to go and run ansible role

## Usage
> ansible-playbook -i hosts site.yml

( I might add -e to provide parameters to provision or have options in global variables, or something similar )

## TODO
- [ ] arch-chroot

- [ ] resolve all TODO in project files

## Similar projects
https://github.com/vvo/ansible-archee

https://github.com/tonyskn/vagrant-arch-ansible
