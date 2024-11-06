# Linux Installation and Package Management

### Boot Partition
```
  /boot partition
    - config-VERSION              config parameters for linux kernel
    - System.map-VERSION          look-up table matching symbol names to corresponding position in memory
    - vmlinux-VERSION             OS kernel proper
    - initrd.img-VERSION          minimal root file systemed loaded into RAM, contains utilities and kernel modules to load real root filesystem
    - boot loader related files   /boot/grub/
```
### GRUB 2
```
  grub-install
    --boot-directory=/boot /dev/sdx

  /boot/grub/grub.cfg              #config file but no editing
  /etc/default/grub                #edit this one
    GRUB_DEFAULT=                  default menu entry to boot, 0,1,saved
    GRUB_SAVEDEFAULT=              if true and GRUB_DEFAULT=saved, then deafult boot wil be last option
    GRUB_TIMEOUT=                  timeout in seconds, before default entry is selected
    GRUB_CMDLINE_LINUX=            list command line options entires for linux kenerl
    GRUB_CMDLINE_LINUX_DEFAULT=    extra parameters added to default entry
    GRUB_ENABLE_CRYPTODISK=        allows to search for encrypted disks

  

```



###
```

```



###
```

```
