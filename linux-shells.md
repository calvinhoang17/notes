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
### Customize shell environment
```
  Assigning variables:       <variable_name>=<variable_value>
  Check variable:            echo $<variable>

  readonly <variable_name>=<variable_value>   #make variable immutable
  set <variable>    #outputs currently assigned variables and functions and 
  unset <variable>  #unset variable local or global
    -v    for variables
    -f    for functions
  export <variable> #set local variable to environment

  Common Environment Variables
    DISPLAY
    HISTCONTROL
    HISTSIZE
    HISTFILESIZE
    HISTFILE
    HOME
    HOSTNAME
    LANG
    LD_LIBRARY_PATH
    MAIL
    MAILCHECK
    PATH
    PS[1 - 4]
    SHELL
    USER

  alias alias_name=command(s)      #create an alias
  unalias alias_name               #remove an alias
  ''      #dynamic expansion
  ""      #static expansion

  function function_name { }
  function_name() { }
    
  Bash special variables:
    $?       expands results of last command run, 0 = sucess, >0 = error
    $$       shell PID
    $!       PID of last background job
    $[0-9]   parameters or arguments neing passed to function
    $#       number of arguments passed to commands
    $@, $*   arguments passed to command
    $_       last parameter or name of script  

```
### Simple scripts
```
  #!      #shebang
  #!/bin/bash          #start of all bash scripts
  chmod +x script.sh   #allow for execution bit

  Bash script parameters
  $*          all arguments passed to the script
  $@          all arugments passed to the script. if double quotes, every argument will be double quotes
  $#          number of arguments
  $0          name of script file
  $!          PID of last executed program
  $$          PID of current shell
  $?          numberical exit status code
  ``          use to store output of a command in a variable

  Arithmetic Expressions
    expr or $(())

  Conditional Execution
    &&        command to right will only be executed if left did not enocunter error
    ||        command will be executed only if previous command did encounter an error
    if fi     if statement
    else      else statement

    echo
      -e      allow special characters output
      \t      align text
      \n      new line output
      
    Extended Tests
      test or [ ]
      -a "$VAR"            if exists in filesystem and is a file
      -b "$VAR"            if is special block file
      -c "$VAR"            if is a directory
      -f "$VAR"            if exists in filesystem
      -g "$VAR"            if has SGID permissions
      -h "$VAR"            if is symbolic link
      -L "$VAR"            if is symbolic link
      -k "$VAR"            if has sticky bit permission
      -p "$VAR"            if is pipe file
      -r "$VAR"            if is readable by current user
      -s "$VAR"            if exists and not empty
      -S "$VAR"            is a socket file
      -t "$VAR"            is open in a terminal
      -u "$VAR"            has SUID permission
      -w "$VAR"            is writable by current user
      -x "$VAR"            is executable by current user
      -O "$VAR"            is owned by current user
      -G "$VAR"            belongs to effective group of current user
      -N "$VAR"            has been modifed since last time accessed
      "$VAR1" -nt "$VAR2"  if VAR1 is newer than VAR2
      "$VAR1" -ot "$VAR2"  if VAR1 is older than VAR2
      "$VAR1" -ef "$VAR2"  if VAR1 is hardlink to VAR2

      Arbitrary text variables
      -z "$TXT"
      Evaluate if variable TXT is empty (zero size).
      
      -n "$TXT" or test "$TXT"
      Evaluate if variable TXT is not empty.
      
      "$TXT1" = "$TXT2" or "$TXT1" == "$TXT2"
      Evaluate if TXT1 and TXT2 are equal.
      
      "$TXT1" != "$TXT2"
      Evaluate if TXT1 and TXT2 are not equal.
      
      "$TXT1" < "$TXT2"
      Evaluate if TXT1 comes before TXT2, in alphabetical order.
      
      "$TXT1" > "$TXT2"
      Evaluate if TXT1 comes after TXT2, in alphabetical order.

      $NUM1 -lt $NUM2
      Evaluate if NUM1 is less than NUM2.
      
      $NUM1 -gt $NUM2
      Evaluate if NUM1 is greater than NUM2.
      
      $NUM1 -le $NUM2
      Evaluate if NUM1 is less or equal to NUM2.
      
      $NUM1 -ge $NUM2
      Evaluate if NUM1 is greater or equal to NUM2.
      
      $NUM1 -eq $NUM2
      Evaluate if NUM1 is equal to NUM2.
      
      $NUM1 -ne $NUM2
      Evaluate if NUM1 is not equal to NUM2.

      ! EXPR
      Evaluate if the expression EXPR is false.
      
      EXPR1 -a EXPR2
      Evaluate if both EXPR1 and EXPR2 are true.
      
      EXPR1 -o EXPR2
      Evaluate if at least one of the two expressions are true.

      case
          ;;
          ;; *)
      esac

      Loop constructs
        for VARNAME in LIST
        do
            COMMANDS
        done

        until, while
```


