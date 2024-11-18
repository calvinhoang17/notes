# Shells 

### Shell
```
  Types of Shells:
      -  Interactive
          -  Interactive login
          -  Interactive non-login
      -  Non-interactive
          -  Non-interactive non-login
          -  Non-interactive login 

  bash
        -l, --login          login shell
        -i                   interactive shell
        --noprofile          ignore system-wide startup file 
        --norc               w/ interactive shells ignore system-wide startup file and user-level startup file
        --rcfile <file>      w/ interactive shells, take <file> as startup file

  su    #change userID or become root
     -, -l, --login [user]  start interactive login shell as [user]
     [user]                 start interactive non-login shell as [user]
     - root, -              start interactive login shell as root
     root,                  start interactive non-login shell as root

  sudo
       su - [user], su -l [user], su --login [user]        start interactive login shell as [user]
       su [user]                                           start interactive non-login shell as [user]
       -u [user] -s                                        start interactive non-login shell as [user]
       su - root, su -                                     start interactive login shell as root
       -i                                                  start interactive login shell as root
       -i <some_commad>                                    start interactive login shell as root, run command then resturn to orginal user
       su root, su                                         start interactive non-login shell as root
       -s, -u root -s                                      start non-login shell as root

  echo $0   #find out what type of shell we are working at
    Interactive login: -bash or -su
    Interactive non-login: bash or /bin/bash
    Non-interactive non-login (scripts): <name_of_scripts>

  ps aux | grep bash      #see how many bash shells up and running

  Startup Files
    Interactive login shell
        Global (/etc)
          /etc/profile        # .profile file
          /etc/profile.d/*    # directory with scripts executed by /etc/profile
    
        user-level (~)
          ~/.bash_profile    # user environment configuration
          ~/.bash_login      # only be executed if no ~/.bash_profile file
          ~/.profile         # check if Bash shell is being run
          ~/.bash_logout     # clean-up operations when exiting shell

    Interactive non-login shell
        Global level (/etc)
            /etc/bash.bashrc    # makes sures being run interactively
        local-level ( ~ )
            ~/.bashrc           # stores user's specfic aliases and functions

    Non-Interactive login shell
    Non-Interactive non-login shell

  SKEL  #variable whose value is the absolute path of skel directory
        #directory servers are template for file system structure of users' hoem directories
        #/etc/adduser.conf  
        
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


### subtitle
```
```
