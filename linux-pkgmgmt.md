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

  Software Repositories
      /etc/apt/sources.list
      /etc/apt/sources.list.d
        #list of sources to know where to get packages from
    
        syntax:  ARCHIVETYPE-URL-DISTRIBUTION-COMPONENETS (main, restricted, universe, multiverse, contrib, non-free, security, backports)
```
### RPM Package Manager (rpm) 
```
  .rpm files

  rpm PACKAGENAME
    -i                install package
    -U                upgrade to newer version
    -F                only upgradge an installed package
    -v                verbose output
    -h                print hash signs # for visual aid
    -e                erase or remove
    -qa               list all installed packages on system
    -qi               get info about an installed package (version number, architecture, install date , packager, summary)
    -ql               list files inside an installed package
    -p                get info from a package that has no benn installed yet
    -qf               query file, must provide full paht
```
### YellowDog Updater Modified (YUM) 
```
  yum search PATTERN
  yum install PACKAGENAME
  yum update PACKAGENAME
  yum whatprovides PACKAGENAME          search for package dependencies
  yum info PACKAGENAME

  /etc/yum.conf
  /etc/yum.repos.d/

  Software Repositories
      yum-config-manager
          --add-repo URL
          --disable updates
          --enable updates
      yum repolist all
```

### DNF
```
    #for of yum

  dnf
    search PATTERN
    info PACKAGENAME
    install PACKAGENAME
    remove PACKAGENAME
    upgrade PACKAGENAME
    provides FILENAME
    list --installed
    repoquery -l PACKAGENAME
    repolist
```

### Zypper
```
  zypper
    refresh         refresh repositories and metadata
    se / search     search for a package
    -i              list installed packages in system
    in              install a package
    rm              remove a package
    info            see metadata associated with a package
    repos           see list of repositories currently registered in system
    modifyrepo      
      -d              disable
      -e              enable
      -F              disable repo autorefresh
      -f              enable repo autorefresh
    addrepo
    removerepo
```
