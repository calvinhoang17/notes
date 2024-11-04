# Linux System Architecture

### Hardware settings
```
  lspci  #shows all devices currently connected to PCI
    -s       specify device
    -v       show more detail
    -k       show kernel module

  lsusb    #lists USB devices currently connected to machine
    -v       show more detail output
    -d       specify device
    -t       show mappings as hierarchical tree
     
  lsmod      #shows all currently loaded modules
  modprobe   #use to load and unload kernal modules
    -r          unload modules
  modinfo    #shows modules desc, file, author, license, and other info
    -p          display only avaiable parameters

  /proc
    -  /cpuinfo      #list detaile info about CPU
    -  /interrupts   #list number of interrupts per IO device
    -  /ioports      #list currently registered input/outpit port regions in use
    -  /dma          #list registered DMA channels in use 
```

### Booting system
```
  BIOS/UEFI -> bootloader -> kernel

  BIOS - Basic Input/Output System
    #first 512 bytes is MBR (Master Boot Record)
    1. POST
    2. BIOS activates basic components - video output, keyboard, storage media
    3. BIOS loads first stage of bootloader from MBR (first 440 bytes)
    4. first stage calls second stage of bootloader - presents boot options and loading kernel

  UEFI - Unified Extensible FIrmware Interface
    #EFI System Partition (ESP)
    1.  POST
    2.  UEFI activates basic components - video output, keyboard, storage media
    3.  UEFI reads definitions in NVRAM to execute bootloader stored in ESP
    4.  if bootloader, load kernel to start OS

  Bootloader
    GRUB (Grand Unified Bootloader)       
      #option=value
      acpi              enables/disables ACPI support
      init              sets alternative system initiator
      systemd.unit      sets systemd tarfet to be activated
      mem               sets amount of available RAM for system
      maxcpus           limit number of processors or cores visible to system
      quiet             hides most boot messages
      vga               selects a video mode
      root              sets root partition
      rootflags         mount options for root filesystem
      ro                makes initial mount of root filesystem read-only
      rw                allow writing in root fiesystem during inital mount
    
      #to make persistent across reboots, add parameters to /etc/default/grub in GRUB_CMDLINE_LINUX
      #to apply changes -> grub-mkconfig -o /boot/grub/grub.cfg

  System Initialization
    bootloader -> loads kernel to RAM -> open initramfs (initial RAM filesystem) -> mount filesystems in /etc/fstab -> execute init

    sysV standard    #service manager based on SysVinit, runlevels 0, 1 , 6 are shared across distro
    systemd          #modern system + service manager
    upstart          #substitue to init

  kernel ring buffer   #memory space where kernel stores its messages
    dmesg
    journalctl
      -b, --boot, -k, --dmesg         shows boot messages
      --list-boots                    shows list of boot numbers relative to current boot, id hash, timestamps
```


### 
```


```



### 
```


```
