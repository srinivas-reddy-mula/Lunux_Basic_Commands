# Introduction to Shell
1. what is kernel?
    * a kernel is core part of OS which acts a a interface b/w user shell commands and H/W.

2. Shell?
    *  shell is part of OS which interacts with Kernel 
        i.e U user command *interacts* with *kernel* using __*shell*__
    Shell converts human readable language into machine understandable format(as in __binary__ format)

3. Types of shell?
    * Bash  (Bourne Again Shell)
    * sh    (Shell)
    * ksh   (Korn Shell)
    * csh   (C Shell)
    * zsh   ( extended Bourne shell with many improvements, including some features of Bash, ksh, and tcsh)
    * nologin (to abondon login to a user)

4. Why shell scripting?
    * shell script can take input from user, file and output them on screen.
    * Useful to create our own commands.
    * Save lots of time.
    * TO automate some task of day to day life.
    * System Administartion part can be also automated.

5. Limitations of Shell Script?
    * Compatibility problems between different platforms.
    * Slow execution speed.
    * A new process launched for almost every shell command executed.

## Editors Availble : vi, nano, emac

## getting help in linux 
    --> help
    --> man
    --> info

6. TO check current shell 
    '''
    echo $0
    tail /etc/passwd
    '''
    * TO list the shells
    '''
    [ec2-user@ip-172-31-20-83 ~]$ cat /etc/shells
    /bin/sh
    /bin/bash
    /usr/bin/sh
    /usr/bin/bash
    [ec2-user@ip-172-31-20-83 ~]$

    '''

7. File permissions
    * Permissions are applied on three levels
        * Owner or User level
        * Group Level
        * Others Level
    
    * Access modes are of three types
        * __*r*__ read only
        * __*w*__ write/edit/delete/append
        * __*x*__ execute/run a command

## important for shell script --> shebang
    !/bin/bash
        or
    #!/usr/bin/perl
        or
    #!/usr/bin/python