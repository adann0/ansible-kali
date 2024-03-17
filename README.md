# ansible-kali

Ansible role to setup Kali Linux.

## Features

- azerty keyboard layout (in vmware and xfreerdp)
- systemd-timesyncd
- fail2ban on openssh server
- python2/python3 with pip and venvs
- custom .zshrc
- hydra compiled from source
- all the tools for the OSCP (gobuster, bloodhound, shellter, impacket, wsgidav, ...)

## Install

1. Edit **ansible.cfg** to set your privkey.
2. Edit **inventory** and/or your DNS to set your Kali host.
3. Download Kali VMWare version, set the RAM, CPUs, GPU and the Network settings. Add a Shared Folder in **~/Documents/Kali**. Then boot the VM. Upgrade the VM if asked.
4. Change default passwords.
5. Enable SSH with `$ systemctl enable --now ssh`.
6. Put your pubkey in **/home/kali/.ssh/authorized_keys**.
7. Run :

```
$ ./kali.yml --ask-become-pass [--ask-pass]
```

## Issues

1. Copy/paste not working.

Run `$ /home/kali/vmware-tools-fix.sh` from VMWare.

2. Shared folders are not mounted.

Run `$ /home/kali/mount-shared-folders.sh`.

