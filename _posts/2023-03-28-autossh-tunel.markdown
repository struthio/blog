---
layout: post
title:  "AutoSSH Tunel for Remote connections"
date:   2023-03-28 20:58:23 +0100
categories: ubuntu ssh tunnel
---

Recently I had problems with one of my remote machines. Apparently the IP address of the machine was changed (for unknown reason) and Port Forwarding no longer worked correctly. This was very problematic, as I lost access to all services HTTP/HTTPS and more important SSH. After gaining access to it through 'emergency manners' I decided to start AutoSSH Tunnel, so no matter what I will always get a connection to the remote machine through SSH.

What was needed is to install AutoSSH

`apt-get install autossh`

Then create Systemd service file so Tunnel is automatically started on every reboot.
<user> is replaced with account name I user for 'automations'.


`sudo vim /etc/systemd/system/autossh@<user>.service`

`
[Unit]
Description=AutoSSH tunnel
After=network.target

[Service]
Environment="AUTOSSH_GATETIME=0"
ExecStart=/usr/bin/autossh -M 20000 -N -p 8022 -o "UserKnownHostsFile=/home/<user>/.ssh/known_hosts" -o "PubkeyAuthentication=yes" -o "PasswordAuthentication=no" -i /home/<user>/.ssh/id_rsa <user>@<host> -R 1022:localhost:22 -C

[Install]
WantedBy=multi-user.target
`

And what is left is to start service
`
systemctl enable autossh@<user>
service autossh@<user> start
`
