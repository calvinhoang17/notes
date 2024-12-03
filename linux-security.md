# Security 

### Security
```
SUID and SGID
  # SUID = 4000 or s/S on owner's execute bit
  # SGID = 2000 or s/s on group's execute bit

  #Find files with SUID and SGID
  find
    -perm numeric-value or -perm symbolic-value       #special permission exclusively
    -perm -numeric-value or -perm -symbolic-value     #special permission and other permissions
    -perm / numeric-value or -perm / symbolic-value   #either special permission and other permissions

Password Management and Aging
  passwd -S or --status

  #Lock user account
    passwd -l <user>
    usermod -L <user>, usermod --lock <user>
    usermod -U <user>, usermod --unlock <user>

  Chage - change age, password management
    chage <user>    #interactive mode
      -l            #list all
      -m <days> <user>, --mindays <days> <user>        #min days between password changes
      -M <days> <user>, --maxdays <days> <user>        #max days password will be valid
      -d <days> <user>, --lastday <days> <user>        #specify # of days since last password change
      -W <days> <user>, --warndays <days> <user>       #remind password will be expired
      -I <days> <user>, --inactive <days> <user>       #specify # of inactive days after password expiration
      -E <date> <user>, --expiredate <date> <user>     #specify date on which account will be locked

   Discovering Open Ports 

```


