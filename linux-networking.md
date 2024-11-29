# Networking Fundamentals

### Internet Protocols
```
/etc/services    #shows standard service ports

Port	Service
  20      FTP (data)
  21      FTP (control)
  22      SSH (Secure Socket Shell)
  23      Telnet (Remote connection without encryption)
  25      SMTP (Simple Mail Transfer Protocol), Sending Mails
  53      DNS (Domain Name System)
  80      HTTP (Hypertext Transfer Protocol)
  110      POP3 (Post Office Protocol), Receiving Mails
  123      NTP (Network Time Protocol)
  139      Netbios
  143      IMAP (Internet Message Access Protocol), Accessing Mails
  161      SNMP (Simple Network Management Protocol)
  162      SNMPTRAP, SNMP Notifications
  389      LDAP (Lightweight Directory Access Protocol)
  443      HTTPS (Secure HTTP)
  465      SMTPS (Secure SMTP)
  514      RSH (Remote Shell)
  636      LDAPS (Secure LDAP)
  993      IMAPS (Secure IMAP)
  995      POP3S (Secure POP3)

```

### Network Config
```
  /etc/network/interfaces
  
  ip link show
  nmcli device 

  Interface Naming:
    en                Ethernet
    ib                InfiniBand
    sl                Serial line IP (slip)
    wl                Wirless local area network (WLAN)
    ww                Wireless wide area netowrk (WWAN)
    eno1              index provided by BIOS or firmware of embedded devices
    ens1              PCI express slot index
    enp3s5            address at corresponding bus
    enx78e7dlea46da   interface's MAC address
    eth0              legacy convention

    /etc/hostname  
    hostnamectl
      set-hostname
      status
      --pretty
      --transient

  /etc/nsswitch.conf        #Name Service Switch config file
  /etc/hosts                #local file of hosts database
  /etc/resolv.conf          #dns resolver config 

  Network Manager
    nmcli
      general
      networking
      radio
      connection
      device
      agent
      monitor

  Systemd-networkd
    /lib/systemd/network
    /run/systemmd/network
    /etc/systemd/network

    
    
```

### Network Troubleshooting
```
```


### Client-side DNS
```
```


