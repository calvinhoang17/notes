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
  stdin             #standard input
  stdout            #standard output
  stderr            #standard error
  cat               #concatenate, outputs stuff
  diff              #shows difference between 2 files
  grep              #filter text
    -v                invert match

  Operators
    >            #direct output
    >>           #append redirection
    |            #pipes

  head              #read first 10 lines
  tail              #read last 10 lines
    -n #              define number of lines to show   
  wc                #word count
    -l                 print number of lines

  sed        #stream editor for filtering and transforming text

  Wildcards
    *        #represents zero, one or more occurrences of any character
    ?        #question mark, represents singel occurence of any character
    [ ]      #represents any occurrence of charcters enclosed in square brackets
    
```
### Data Integriy
```
  sha256sum  FILE
    -c        
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
