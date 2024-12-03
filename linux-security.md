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
  lsof - list open files
    -i        print all Internet network files
      @ip-address
      :port
  
  fuser .  
    -v        verbose
    -n        network port/sockets

  netstat
    -l, --listening        #list listening ports and sockets
    -t, --tcp
    -u, --udp
    -e, --extend           #extended information
    -n, --numeric          #print only port numbers and IP addresses

  nmap  #host scanner
    -p          #define port
    -F          #run fast scan on 100 most common ports
    -v, -vv     #vervbose

  ulimit  #user limit on OS
    -a, -Sa        display soft limits
    -Ha            display hard limits
    -b             max socket buffer size
    -f             max size of files written by shell and its children
    -l             max size locked into memory
    -m             max RSS - current portion of memory held by a process in RAM
    -v             max amount of virtual memory
    -u             max number of process available to single user
  
Logged in Users
  last          #prints listing of last logged in users
  who           #shows currently logged in users
    -b,--boot      display last system boot
    -r,--runlevel  display current runlevel
    -H,--heading   print column heading

Sudo
  su - <target-username>

  /etc/sudoers
  sudo useradd -aG sudo <user>  
  
     
```


