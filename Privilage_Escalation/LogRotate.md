Log rotate is used to save space when storing logs.. allows to change the 
size of log
age of log
action to take when a factor is reached. 

**Conf**
/etc/logrotate.conf

**Force New Rotation**
To force a new rotation on the same day, 
we can set the date after the individual log files in the status file /var/lib/logrotate.status or use the -f/--force option:

**Conf**
We can find the corresponding configuration files in /etc/logrotate.d/ directory.

**To exploit logrotate, we need some requirements that we have to fulfill.**

    we need write permissions on the log files
    logrotate must run as a privileged user or root
    vulnerable versions:
        3.8.6
        3.11.0
        3.15.0
        3.18.0
