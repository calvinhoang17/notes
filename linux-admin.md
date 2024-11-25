# Administrative Tasks

### User and Group Accounts 
```
  /etc/shadow

  useradd [options] NAME    #create a new user
    -c                       with custom comments
    -d                       with custom home directory
    -e                       set specific date on which it will be disabled
    -f                       set number of days password will expire and cause account to be disable
    -g                       with specfic GID
    -G                       add mulitple secondary groups
    -k                       copy skeleton files from specfic custom directory (needs -m or --create-home)
    -m                       with home directory
    -M                       without home directory
    -s                       with specfic login shell
    -u                       with specific UID
    
  passwd NAME     #change password of user
  id NAME         #check UID,GID and groups of user
  groups NAME     # check group of user

  usermod [options] NAME     #change attribute of existing user account
    -c                        add brief comment
    -d                        change home directory (w/ -m, contents of home dir is moved)
    -e                        set expiration date
    -f                        set # of days password expires
    -g                        change primary group
    -G                        add secondary group
    -l                        change login name
    -L                        lock account
    -s                        change login shell
    -u                        change UID
    -U                        unlock account

  userdel [options] NAME    #delete user account
    -r                       removes home directory and contents of user

  groupadd GROUP            #add group
  groupmod GROUP            #modify group
  groupdel GROUP            #delete group

  /etc/login.defs              #configuration file that controls creation of users and groups
    UID_MIN and UID_MAX        range of user IDs that can be assigned
    GID_MIN and GID_MAX        range of group IDs that can be assigned 
    CREATE_HOME                specify whether a home directory should be created
    USERGROUPS_ENAB            specify whether default create new group for each user account and delete if user is removed
    MAIL_DIR                   mail spool directory
    PASS_MAX_DAYS              max number of days password may be used
    PASS_MIN_DAYS              min number of days between password changes
    PASS_MIN_LEN               min acceptable password lengthl
    PASS_WARN_AGE              number of warning days before password expires

  passwd [options] USER        #change user's password
    -d                          delete password of user (disables account)
    -e                          force user to change password
    -i                          set number of days of inactivity after password expires
    -l                          lock user account
    -n                          set miniumum password lifetime
    -S                          output information about password status
    -u                          unlock user account
    -x                          set maxiumum password lifetime
    -w                          set number of days of warning before password expires

  chage [options] USER          #change age, change passworf aging info of a user
    -d                           set last password change
    -E                           set expiration date
    -I                           set number of days of inactivity
    -m                           set minimum password lifetime
    -M                           set maxium password lifetime
    -W                           set number of days of warning before password expires

  /etc
    -  /passwd              #basic information about users
    -  /group               #basic information about groups
    -  /shadow              #contains encrypted user passwords
    -  /gshadow             #contains encrypted group passwords

  /etc/passwd      username:password:UID:GID:GECOS:homedirectory:shell
  /etc/group       groupname:grouppassword:GID:memberlist
  /etc/shadow      username:encryptedpassword:dateoflastpasswordchange:minpasswordage:maxpasswordage:passwordwarningperiod:passwordinactvityperiod:expirationdate:reservedfield
  /etc/gshadow     groupname:encryptedpassword:groupadmins:groupmembers

  getent [option] NAME    #display enries from databases
  

```

### Automate tasks by scheduling jobs
```
  /etc/crontab
  
  User crontabs    #/var/spool/cron
  System crontabs  #/etc/crontab, /etc/cron.d

  *  (asterik) refers to any value
  ,  (comma)   specifies list of possible values
  -  (dash)    specifies range of possible values
  /  (slash)   specficies stepped values

  /etc/cron.hourly
  /etc/cron.daily
  /etc/cron.weekly
  /etc/cron.monthly

  @reboot                run specified task afte reboot
  @hourly                run specfied task once an hour at beginning of hour
  @daily or @midnight    run specfied task once a day at midnight
  @weekly                run specfied task once a week at midnight on Sunday
  @monthly               run specfied task once a month at midnight on first day of month
  @yearly or @annually   run specfied task once a year at midnight on 1st of january

  Variables:
  HOME        directory where cron invokes commands
  MAILTO      name of user or address where std output and error is mailed to
  PATH        path where commands can be found
  SHELL       shell to use

  crontab -e      #to edit crontabe file 
    -l            display current crontab
    -r            remove current crontab
    -u            specify name of user crontabe

  Access to job scheduling
    /etc/cron.allow
    /etc/cron.deny

  Systemd Timers
    /etc/systemd/system/foobar.service
    /etc/systemd/system/foobar.timer

    [Timer]
    OnCalendar= DayOfWeek Year-Month-Day Hour:Minute:Second

    systemctl enable foobar.timer
    systemctl start foobar.timer

```

### subtitle
```
```


### subtitle
```
```


### subtitle
```
```