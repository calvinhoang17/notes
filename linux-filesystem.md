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
















```
