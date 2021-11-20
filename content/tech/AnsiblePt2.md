---
title: "Ansible ala Macbook"
date: 2021-11-14T07:51:41-05:00
tags: ["blog","tech","ansible"]
description: "Ansible controlled via MacBook"
---

My new Macbook Air is now my primary computer so I'm going to use it as my controller for all things Ansible.  Here is essentially a cheat sheet.

# Playbooks

Here is a current list of playbooks that I use and what they do:

+ CheckForUpdates.yaml - Simply check for updates and show the output from each server.  I still would like to format the output somehow to clean it up and only displays the important stuff.
+ DockerDown.yaml - I have two servers that use Docker.  Sometimes, I need to send a "docker-compose down" to safely stop my containers.
+ Install.yaml - All of my servers are Ubuntu so this playbook uses the Apt module to install single or multiple packages.
+ IsPackageInstalled.yaml - A simple check to see if a defined package is installed.
+ RebootServers.yaml - Once updates are done or if things are getting gnarly, send a simple reboot to all servers.  I still want to reformat this to send "docker-compose down" to only my Docker servers, then send the reboot command.
+ ShutdownServers.yaml - Only if I'm performing maintenance to my virtual host.
+ UpdateServers.yaml - Using the Apt module, update the Apt cache, check for updates and update all available updates.  Did I mention it updates?

# Running Playbooks

Run a Playbook on all servers:

> sudo ansible-playbook checkforupdates.yaml -i servers -u USERNAME -K

Run a Playbook on only one server:

> sudo ansible-playbook install.yaml SERVER -u USERNAME -K



