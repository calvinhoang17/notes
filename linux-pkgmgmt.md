# Linux Package Management

### Debian Package Tool (dpkg)
```
  .deb files

  dpkg PACKAGENAME
    -i                   to install package
    -r                   to remove package
    -P                   to purge everything associated with package
    -I                   to inspect package, shows version, maintainer, dependencies and more
    --get-selections     list every package installed on your system
    -L                   list every file installed by a specific package

    dpkg-query -S PATHTOPACKAGE        #find out which package owns a specfic file in system
    dpkg-reconfigure PACKAGE           #restore package's settings to fresh state
```

### Advanced PAckage Tool (apt) 
```
  .deb files

  apt-get          #to download, install, upgrade or remove packages from system
    update            update package index
    install           install a package
      -f                fix broken packages by installing missing dependencies
    remove            remove a package
    purge             remove package and any config files
    upgrade           auto upgrade any installed packages
      -y                yes to all
    clean              empty cache - /var/cache/apt/archives + /var/cache/apt/archvies/partial/

  apt-cache        #to perform operations, like searches, in package index
    search          conduct a search
    show            shows info of package

  apt-file         #for searching files inside packages
    update          update package cache
    list            list contents of a package
    search          search all packages for a file
  
  /etc/apt/sources.list
  /etc/apt/sources.list.d
    #list of sources to know where to get packages from

    syntax:  ARCHIVETYPE-URL-DISTRIBUTION-COMPONENETS (main, restricted, universe, multiverse, contrib, non-free, security, backports)
```
### Advanced PAckage Tool (apt) 
```
```
### Advanced PAckage Tool (apt) 
```
```
