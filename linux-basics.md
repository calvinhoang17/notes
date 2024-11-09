# Linux - Basics

### Get System Info
```
  pwd       #print working directory
  uname     #print system information
    -a              all
    -s              kernel name
```

### Command Info
```
  man        #command documentation
  apropos    #search manual pages and documenation
  history    #show previous command history
```

### Environment Variables
```
  env        #shows enviroment variables
  $VARIABLE
  VARIABLE=INPUT      #create custom variable
  export VARIABLE     #pass variable to any child shells
  unset VARIABLE      #delete variable
  set        #output al variables and functions
```

### Basic File Commands
```
  touch OPTIONS FILE_NAME        #create file
    -a      changes access time
    -m      changes modification time

  ls OPTIONS FILE    #list directory contents
    -l     long listing, shows permissions, owner, size, modified date, time, name
    -h     human readable format
    -a     list all files including hidden
    -R     recurisive 

  cp OPTIONS SOURCE DESTINATION    #copy files
    -r     recursive

  mv FILENAME DESTINATION_DIRECTORY    #move files
    -i    ask confirmation
    -f    force
     
  rm OPTIONS FILE    #remove contents    #remove files
    -i    ask confirmation
    -f    force
    -r    recursive

  mkdir OPTIONS DIRECTORY_NAME      #make directory
    -p     parents, create directory with subdirectories

  rmdir OPTIONS DIRETROY            #remove directory
    
```

### Text Manipulation
```
  Alphanumeric charcters (a-z, 0-9)
  Escape charcters
    ""              #will preserve all characters expect $ ,` ,\ , !
    ''              #will preserve literal value of all characters

  Redirects
    stdin             #standard input    0 
    stdout            #standard output   1  
    stderr            #standard error    2

    &> or >&          redirect stdout and stderr
    /dev/null         blackhole

    >            #direct output
    <            #redirect right to left
    >>           #append redirection
    <<           #Here document and Here string method
    |            #pipes
    ``           #command substitution - output


  cat               #concatenate, outputs stuff
  diff              #shows difference between 2 files
  grep              #filter text
    -v                invert match
  head              #read first 10 lines
  tail              #read last 10 lines
    -n #              define number of lines to show   
  wc                #word count
    -l                 print number of lines
  tee               #display output on screen

  sed        #stream editor for filtering and transforming text

  Wildcards
    *        #represents zero, one or more occurrences of any character
    ?        #question mark, represents singel occurence of any character
    [ ]      #represents any occurrence of charcters enclosed in square brackets
    
```
### Find Files
```
  find STARTING_PATH OPTIONS EXPRESSION
    -name        search by name
    -type f      file search
    -type d      directory search
    -type l      symbolic link search
    -iname       by name, case insensitive
    -not         return results that do not match
    -maxdepth N  searches directory N levels deep
    -mtime N     search by modfication time
    -size (+,-)  search by size
    -exec        perform action after search
    -delete      delete files
```
### Archive Files
```
  tar -cvf NAME.tar PATH
    -c        create an archive
    -v        verbose mode
    -f        specify filename
    -x        extract archive
    -z        use gzip algorithm (.tar.gz or .tgz)
    -j        use bzip2 algorithm (.tar.bz2, .tar.bz, .tbz)

  gzip FILE-TO-COMPRESS
    #.gz file
    #removes original files after compressing
    gunzip       to uncompress
  bzip2 FILE-TO-COMPRESS
    bunzip2       to uncompressed
    #similar to gzip

  cpio        #copy in, copy out - .cpio or .tar
    -o          output
    -i          extract
    -d          create destination folder

  dd  if=oldfile of=newfile
    conv=ucase        changing case
    
```
### Processes
```
  jobs
    -l        display process ID (PID)
    -n        list only processes changed since last notification
    -p        list process ID
    -r        list only running jobs
    -s        list only stopped jobs
    %n        jobs with id number n
    %?str     jobs whose command line contains str
    %+ %%     current job
    %-        previous jobs

  fg        #take job to foreground
  bg        #take job to background
  &         #use with commands to take job to bg
  kill      #SIGTERM

  nohup COMMAND &        #detacj jobs from sessions

  watch    #allows to watch program output overtime
    -n        interval
  
  pgrep PROCESS      #find PID of a procress
  pkill PROCESS      #kill a process by name

```




### subtitle
```
```
