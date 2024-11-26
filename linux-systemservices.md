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



```

### Mail Transfer Agent (MTA)
```



```

### Manage printers and printing
```



```
