---
title: "SystemD Services and Timers"
date: 2022-05-19
---

# How I Backup Steam on Linux

One thing that I've come to learn and enjoy is that my Operating System needs to be treated as disposable.  It shouldn't matter what distribution I use on my desktop PC, I should be able to easily restore my data using a handful of tools.  Most people back up their Dot Files and scripts to Git, or keep their documents in the cloud or on another server; I am one of those people.  But what about "special" things like your Steam library?  I am blessed to have a Gigabit Internet connection where I live so downloading games isn't a problem.  However, it is nice to have a local copy on the server.

# Goal

Have a 1:1 backup of my SteamApps folder on my server.

# How I Wanted It To Work

My "Windows" brain initially thought that I would have to setup and use the following:

+ Create a network share on my server
+ Create/Allow permissions
+ Setup a script to copy files and folders
+ Schedule to run daily

I quickly found that this is not the way to think in the Linux world.  Many Linux tools have some amazing features and options that can help you get the job done in less time, less code, less setup.

# How It Should Work

## Tools

The tools that I use:


+ RSync
+ SystemD Services and Timers


First, RSync has built in SSH capabilities.  The trick is that you need to have an existing SSH Key Pair setup in order for it to work.  Then, you can specify your SSH key as an option in the RSync command.  My example below shows the proper command with a SSH Key Pair using default values:

*/usr/bin/SteamBackup.sh*
```
#!/bin/sh
rsync -avzhe "ssh -i /home/USER/.ssh/id_rsa" --delete-before /home/USER/.steam/steam/steamapps/ remote_user@IP_OF_SERVER:/storage/Steam
```

This command lives in a Shell Script located under ```/usr/bin``` and set to be executable:

```sudo chmod a+x /usr/bin/SteamBackup.sh```

I ran this manually a few times over a span of days to make sure that it was going to do what I wanted it to do.  Now it's time to schedule and automate it.

Next, I created a SystemD service that will run the script upon start:

*/etc/systemd/system/SteamBackup.service*
```
[Unit]
Description=Backup Steam
Wants=SteamBackup.timer

[Service]
Type=oneshot
ExecStart=/usr/bin/SteamBackup.sh

[Install]
WantedBy=multi-user.target
```

Enable the service:

```systemctl enable SteamBackup.service```

Finally, create the timer:

*/etc/systemd/system/SteamBackup.timer*

```
[Unit]
Description=Run Steam Backup Daily
Requires=SteamBackup.service

[Timer]
Unit=SteamBackup.service
OnCalendar=*-*-* *:12:00

[Install]
WantedBy=timers.target
```

Enable the timer:
```systemctl enable SteamBackup.timer```

At this point, you have a timer scheduled to start the Steam Backup service daily at 12:00PM.  If you want to see the logs produced by either the timer or service, run `journalctl`:

```journalctl -S today -f -u SteamBackup.timer```

```journalctl -S today -f -u SteamBackup.service```

# Conclusion

I've been used to creating simple CronJobs before but since things are going the way of SystemD, I might as well adapt.  There are obviously other ways to schedule scripts to run at a certain time or even in a GUI, but it's just not as fun as the CLI way.