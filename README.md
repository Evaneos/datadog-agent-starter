# Datadog Monitoring Agent starter

Since the version 6 of their agent, Datadog does not provide SysVinit scripts to start their agent. Only Systemd and Upstart config, to surely benefits from the process monitoring from both system.

This project's goal is to provide ways to start the Datadog Monitoring Agent in an old system.

## SysVinit script

This script is mostly based on the skeleton from the Debian Wheezy's [initscripts](https://packages.debian.org/wheezy/initscripts).

As an good old sysinit script, it does not monitor the started process... So, if it dies for whatever reason, you're good to restart it. This can be done with process monitoring (Nagios, Monit...)... but you may expect some delay to catch the critical issue. That's why, we could use a process supervisor to overcome this issue.

## Supervisord program

This little configuration describe a way to supervise you Datadog Monitoring Agent. This should be good enought to be sure the agent keeps monitoring.

## Todo

While those configurations have been tested on a Debian wheezy, by hand (with a Vagrant's wheezy64 box), it would be a good idea to add automated tests.