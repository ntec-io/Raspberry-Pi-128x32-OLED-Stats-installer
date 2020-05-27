# Raspberry Pi 128x32 OLED Stats installer

## What it does
This ansible playbook installs all neccessary dependencies and configurations for using an OLED. It also copies all neccessary scripts and files to the raspberries and creates and enables a systemd service called `pi-oled`.

## How to use
1. Install `ansible`
2. Change the hostnames (or ips) in `host.ini` to those of your raspberries.
3. Change the `remote_user` in `ansible.cfg` to the username of your raspberries (make sure they can sudo)
4. Run the playbook `ansible-playbook main.yml`

## Manual control
Disable automatic start: `sudo systemctl pi-oled disable` (on every raspberry)

Stop service: `sudo systemctl pi-oled stop`