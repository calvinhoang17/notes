# Linux Filesystem

### Create partitions and filesystems
```
fdisk TARGET
  w          write
  q          quit without saving changes
  p          print current partition table
  n          create a partition
  F          show unllocated space
  d          delete a partition
  t[x]       change partition type
  l          list valid partition codes

gdisk TARGET
  p          print current partition table
  n          create a partition
  d          delete a partition
  b,c        rebuild corrupt main GPT header or partition table
  d,e        rebuild a backup of GPT header or partition table
  f,g          convert MBR to GPT / vice-versa

mkfs.ext[x] TARGET
mke2fs - t EXTENSION TARGET  
  -b SIZE           set block size (1028, 2048, 4096)
  -c                check for bad blocks before creating fs
  -d DIRECTORY      copies directory to new disk
  -F                force
  -L VOLUME_LABEL   set volume label
  -q                quiet mode
  -U ID             set UUID
  -V                verbose mode

mkfs.xfs TARGET
  -b size=VALUE    set block size
  -m crc=VALUE     1 = enable or 0 = disable / enable CRC32c checks to verify integrity of metadata on disk
  -m uuid=VALUE    sets partition UUID
  -f               force creation
  -l logdev=DEVICE put log section of filesystem on specified device
  -l size=VALUE    set size of log
  -q               quiet mode
  -L LABEL         set filesystem label
  -N               prints all parmeters wihout actual creation

mkfs.exfat TARGET
  -i VOL_ID        sets volume ID
  -n NAME          sets volume name
  -p SECTOR        specifie first sector
  -s SECTORS       defines number of physical sectors

mkfs.btrfs TARGET
  -L LABEL        set label
  -m DEVICES      pass mulitple devices (raid0, raid1, raid5, raid6, raid10, single, dup)

  Creating btrfs subvolume
    btrsfs subvolume create TARGET
    btrsfs subvolume show TARGET

parted DEVICE
  select DEVICE
  print                               show more info
  print devices                       show all devices
  print free                          show free devices
  mklabel (msdos, gpt)                create partition table
  mkpart PARTTYPE FSTYPE START END    create partition
  rm DEVICE                           to remove a device
  rescue START END                    recover partition
  resizepart START END                resize partition
  resize2fs DEVICE SIZE               resize filesystem
  mkswap TARGET                       create swap partition
  swapon TARGET                       enable swap partition
  
mount -t TYPE DEVICE MOUNTPOINT
  -a        mount all filesystems listed in /etc/fstab
  -o        pass a list of comma-separated mount options
  -r -ro    mount as read-only
  -w -rw    mount as writeable

unmount MOUNTPOINT
  -a        unmount all filesystmes in /etc/fstab
  -f        force unmounting
  -r        if cannot unmount, will try to make it read-only

lsof DEVICE
  shows list of processes accesing the files currently

/etc/fstab
  FILESSYSTEM MOUNTPOINT TYPE OPTIONS DUMP PASS
  
  OPTIONS
    atime / noatime           access time information
    auto / noauto             can or cannot be mounted automatically with -a
    defaults                  pass options rw, suid, dev, exec, auto, nouser, async to mount
    dev / nodev               whether character or block devices in mounted filesystem should be interpreted
    exec / noexec             allow or deny permission to execute binaries on filesystem
    user / nouser             allows or not an ordianary user to mount fileysystem
    group                     allows a user to mount filesystem if user belongs in owning group
    owner                     allows a user to mount filesystem if user owns device
    suid / nosuid             allow or not SETUID and SETGID bits to take effect
    ro / rw                   mount a filesystem as read-only or writable
    remount                   use with -o to remount with different options
    sync / async              do all I/O ops to filesystem synchronously or asynchronously

```
### File permissions and ownership
```
  ls
    -l       long form
    -d       directory
    -a       show hidden files (.)

 drwxrwxrwx -   filetype-owner(u)-group(g)-others(o)

  Filetypes
    -       normal file
    d       directory
    l       symbolic link
    b       block device
    c       character device
    s       socket

  Permissions
    r       read, 4
    w       write, 2
    x       execute, 1

  chmod PERMISSION FILENAME
    -R      recursive

    symbolic mode
      u,g,o,a / +,-,= / r,w,x
    ocatal mode
      r = 4, w = 2, x = 1, - = 0

  chown USERNAME:GROUPNAME FILENAME
  chgrp GROUPNAME FILENAME
  getent group
  groups USER
  groupmems -g GROUP -l

  umask
    -S      show symbolic mode

  *Special Permissions

    Sticky bit (restricted deletion flag)
      1, t

    Set GID (SGID, Set Group ID)
      2, s on group 

    Set UID (SUID, Set User ID)
      4, s on user 
```
### Hard and symbolic links
```
  Symbolic link (soft links)
    #point to the path of another file
  Hard link
    #second name, additional entry in filesystem pointing to the same place (inode) on disk

  ln TARGET LINK_NAME
    -s       create symbolic link
```
### Filesystem Hierarchy Standard
```
  /                  root directory
    /bin               essential binaries, avaiable to all users
    /boot              boot process files, initrd + linux kernel
    /dev               device files
    /etc               host-specfic configuration files
    /home              users home directory
    /lib               shared libraries needed to boot OS and run binaries under /bin /sbin
    /media             user-mountable media - USB, CD, memeory cards, external disk
    /mnt               mount point for temp mounted filesystems
    /opt               application software packages
    /root              root home directory
    /run               run-time variable data
    /sbin              system binaries
    /srv               data served by system
    /tmp               temporary files
    /usr               read-only user data
    /proc              virtual filesystem containing data related to running processes
    /var               variable data written during system operation - logs, cache,

  find LOCATION PARAMETERS
    -name              filter by name
    -iname             case-insensitive of -name
    -maxdepth N        set subdirectory search level
    -mindepth N        minimum depth
    -mount             avoid mounted filsystem
    -fstype            filter by filesystem
    -user              match by owner user
    -group             match by owner group
    -readable          match files readable by current user
    -writable          match files writable by current user
    -perm NNNN         match by permissions
    -empty             will match empty files and directories
    -size N            match by N file size
    -amin N, -cmin N, -mmin N
    -atime N, -ctime N, -mtime N

  locate
    updatedb
    -i               case-insensitive
    -A               match ALL
    -c               show count

  which
    -a               show all pathnames matching

  type
    -a               show all pathnames matching
    -t               show file type of command

  whereis
    -b               limit to binaries
    -m               limit to man pages
    -s               limit to source code
```
