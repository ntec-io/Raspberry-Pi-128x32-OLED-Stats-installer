# Raspberry Pi 128x32 OLED Stats installer

## What it does
This ansible playbook installs all neccessary dependencies and configurations for using an OLED. It also copies all neccessary scripts and files to the raspberries and creates and enables a systemd service called `pi-oled`.

## How to use
1. Install `ansible` on your local machine: 
https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
2. Change the hostnames (or ips) in `hosts.ini` to those of your raspberries.
3. Change the `remote_user` in `ansible.cfg` to the username of your raspberries (make sure they can sudo)
4. Run the playbook `ansible-playbook main.yml`

## Manual control
Disable automatic start: `sudo systemctl pi-oled disable` (on every raspberry)

Stop service: `sudo systemctl pi-oled stop`

## Advanced
### Using ssh-keys
1. Generate a new ssh key with `ssh-keygen` and follow the instructions but **use a passphrase!** (much more secure)
2. Copy the ssh-key to every machine with `ssh-copy-id <username>@<ip/hostname>` (e.g. `ssh-copy-id pi@raspberry`)
