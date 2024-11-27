# Essential System Services

### Maintain System time
```
  date
    -u            view current UTC time
    -I            IS0 8601 format
    -R            RFC 5322 format
    --rfc-3339    RFC 3339 format
    +%s           Unix time
    --date        use to format a time
    --debug       debug mode
    -s or --set   set timezone

  hwclock
    --set --date
    --verbose

  timedatectl
    set-time
    list-timezones
    set-timezone
    set-ntp no        #disable NTP
    show-timesync --all    #shows status of sntp synchronisation
    

  /usr/share/zoneinfo  -> /etc/localtime

  hwlock --systohc      #set hardware clock from system clock

  /etc/timezone

  NTPD
    # TCP port 123
    # /etc/ntp.conf

    ntpdate pool.ntp.org  #perform inital one-time synchronisation

  ntpq        #utiliy tool for monitoring status fo NTP
    -p        print
    -n        return IP addresses  

  chrony
    chronyc tracking    #info about NTP and system time
    chronyc ntpdata     #detailed info about last valid NTP update
    chronyc sources     #info about NTP servers used
    chronyc makestep    #manually step system clock

    # /etc/chrony.conf
    
```

### System logging
```
  syslog
  syslog-ng  (syslog new generation)
  rsyslog    (rocket-fast system for log processing)

  #  /var/log
  /auth.log        auth process: logges users, sudo info, cron jobs, failed login attempts
  /syslog          centralized file for all logs
  /debug           debug info
  /messages        info messages not related to kernel but other services
  /daemon.log      info relared to daemons or services
  /mail.log        info related to email server
  /Xorg.0.log      info related to graphics card
  /wtmp            sucessful logins
  /btmp            unsucessful logins
  /faillog         failed authentication attempts
  /lastlog         date and time of recent user logins

  zless or zmore     #used for compressed log files

  to view:
    /var/log/wtmp        who or w
    /var/log/btmp        utmpdump or last -f
    /var/log/faillog     faillog
    /var/log/lastlog     lastlog

  rsyslog
    #  /etc/rsyslog.conf.d

  logrotate
    /etc/cron.daily/logrotate      #cronjob
    /etc/logrotate.conf            #config file
    /etc/logrotate.d

  systemd-journald
    # /etc/systemd/journald.conf

    journalctl
      -r                              reverse order
      -f                              live-mode, most recent
      -e                              jump to end
      -n <value>, --lines=<value>     show specify lines
      -k, --dmesg
      --list-boots                    list all available boots
      -b, --boot                      shows all message from current boot
      -p                              filter by serverity/priority
      --since, --until                filter by time, YYYY-MM-DD HH:MM:SS
      /path/to/executable             filter by specfified unit
      <field-name>=<value>            PRIORITY=, SySLOG_FACILITY=, _PID=, _BOOT_ID=, _TRANSPORT=,
      --disk-usage                    check file size
      --vaccum-time=                  eliminate all messages from specified time
      --vaccum-size=                  eliminate all messages from specfifed size
      --vaccum-files=                 eliminate all messages from x file
      --flush (SIGUSR1)               flush jounral from /run/ to /var/
      --sync (SIGRTMIN+1)             request all unwritten log data to be written to disk
      -D </path/to/dir>, --directory=</path/to/dir>
      -m, --merge                     merges entries from all availabe under /var/log/journal
      --file                          define file
      --root                          root directory

      systemd-cat    #manual send logs
```

### Manage printers and printing
```
  CUPS - Common Unix Printing System
    /etc/cups/cupsd.conf         #CUPS config file
    /etc/printcap                #legacy file used by LPD protocol - backward comp
    /etc/cups/printers.conf      #file contains each printer configured
    /etc/cups/ppd                #directory that holds PostScript Printer Description (PPD) files
    /var/log/cups

    


```
