###  basic Linux commands 
*    This Post Contains the use and explaination of below commands,

    whoami
    users
    who
    w
    echo
    date
    cal
    man
    info
    whatis

    So let’s get started.
    
    
##      1.whoami


   
 __It shows the name of the user with whom you logged in i.e, to identify your username whoami command is used.__
    __Example: if you are logged in as a root user and you use this command, the value returned will be “root“__

    [root@devopsage ~]# whoami
    root
    [root@ddevopsage ~]#


###     2.  users

 __It prints out the Ids of the currently logged in users in your host server.__

    [root@devopsage ~]# users
    sampleuser
    [root@devopsage ~]#


###     3. who

 __Who command is also used to list out the logged in users like user command does, but only the__
    **difference is that who command lists the logged in users along with some detailed format.**

    It displays,

        Users login name
        login terminal (tty)
        Login date and time.
        Users IP address


            [root@devopsage ~]# who
            sampleuser1     pts/0        2018-02-24 07:58 (157.48.246.125)
            sampleuser2     pts/1        2018-02-24 08:13 (localhost)


* __Here, the 1st column shows the username, the 2nd column shows their terminal, the 3rd column shows date,__
    __the 4th   column shows time and the 5th column shows the machine Ip address from where they are logged in.__


        Options:

            -H:  prints the column header
            -u:  Will print with some more details like PID and IDLE time.
            -b: this options indicate the time and date of the last reboot



###     4. w

* This command will also show the logged in user along with what users are doing. 
* Linux keeps a track of which users are logged in and what they are doing at that time.
* __w__ commands list out the logged in users and also displays what processes they are running.

        [root@devopsage ~]# w
        08:32:19 up  1:06,  2 users,  load average: 0.00, 0.01, 0.05
        USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
        sampleuser1     pts/0    157.48.246.125   07:58    8:43   0.05s  0.18s sshd: sampleuser1 [priv]   
        sampleuser2     pts/3    localhost        08:36    4.00s  0.00s  0.00s ping localhost   
        [root@devopsage ~]#
    


###     5. echo
    
* echo command is used to print the output of any message on the screen it is also used to print the value
     of certain variables.

   
        [root@devopsage ~]# echo "welcome to devopsage"
        welcome to devopsage

        [root@devopsage ~]# echo $HOME
        /root
        [root@devopsage ~]#
   


###     6. date

* date command is used to display the date and time of the server.
     **It is also used to set the date on the server**


        [root@devopsage ~]# date
        Sat Feb 24 08:48:08 UTC 2018
        [root@devopsage ~]#

* Options:

        %m: month of the year (01-12)
        %d: day of the month (01-31)
        %y: last two digits of the year (00-99)
        %D: date as mm/dd/yy format
        %n: displays output at new line
        %S: second (0-59)
        %M: minute (0-59)
        %H: hour (0-23)
        %T: time as HH:MM:SS
        %j: day of year (001-365)
        %w: day of the week (0-6) //0 is sunday
        %a: weekdays (sun-sat)
        %h: month (jan-dec)
        %r: 12 hour time format. ex: 09:00:03 AM


                [root@devopsage ~]# date
                Sat Feb 24 09:05:47 UTC 2018



                [root@devopsage ~]# date '+%m/%d/%y %H:%M:%S'
                02/24/18 09:05:49


                
                [root@devopsage ~]# date '+%m/%d/%y %n%H:%M:%S'
                02/24/18 
                09:06:07



####    7. cal

* cal command displays the calendar for the current month. It can also display entire year calendar for the mentioned     year or a single month calendar for the mentioned month and year.

Options:

    -j:  Displays Julian dates  (1-365), starting from 1st January
    -m: Display Monday as the first day of the week
    -y:  Display whole year
    -v: Display calendar source.


            [root@devopsage ~]# cal
                February 2018   
            Su Mo Tu We Th Fr Sa
                        1  2  3
            4  5  6  7  8  9 10
            11 12 13 14 15 16 17
            18 19 20 21 22 23 24
            25 26 27 28



                    [root@devopsage ~]# cal 1 2018
                        January 2018    
                    Su Mo Tu We Th Fr Sa
                        1  2  3  4  5  6
                    7  8  9 10 11 12 13
                    14 15 16 17 18 19 20
                    21 22 23 24 25 26 27
                    28 29 30 31



        [root@devopsage ~]# cal 2018
                                    2018                               

            January               February                 March       
        Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa
            1  2  3  4  5  6                1  2  3                1  2  3
        7  8  9 10 11 12 13    4  5  6  7  8  9 10    4  5  6  7  8  9 10
        14 15 16 17 18 19 20   11 12 13 14 15 16 17   11 12 13 14 15 16 17
        21 22 23 24 25 26 27   18 19 20 21 22 23 24   18 19 20 21 22 23 24
        28 29 30 31            25 26 27 28            25 26 27 28 29 30 31

                April                   May                   June        
        Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa
        1  2  3  4  5  6  7          1  2  3  4  5                   1  2
        8  9 10 11 12 13 14    6  7  8  9 10 11 12    3  4  5  6  7  8  9
        15 16 17 18 19 20 21   13 14 15 16 17 18 19   10 11 12 13 14 15 16
        22 23 24 25 26 27 28   20 21 22 23 24 25 26   17 18 19 20 21 22 23
        29 30                  27 28 29 30 31         24 25 26 27 28 29 30

                July                  August                September     
        Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa
        1  2  3  4  5  6  7             1  2  3  4                      1
        8  9 10 11 12 13 14    5  6  7  8  9 10 11    2  3  4  5  6  7  8
        15 16 17 18 19 20 21   12 13 14 15 16 17 18    9 10 11 12 13 14 15
        22 23 24 25 26 27 28   19 20 21 22 23 24 25   16 17 18 19 20 21 22
        29 30 31               26 27 28 29 30 31      23 24 25 26 27 28 29
                                                    30
            October               November               December      
        Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa
            1  2  3  4  5  6                1  2  3                      1
        7  8  9 10 11 12 13    4  5  6  7  8  9 10    2  3  4  5  6  7  8
        14 15 16 17 18 19 20   11 12 13 14 15 16 17    9 10 11 12 13 14 15
        21 22 23 24 25 26 27   18 19 20 21 22 23 24   16 17 18 19 20 21 22
        28 29 30 31            25 26 27 28 29 30      23 24 25 26 27 28 29
                                                    30 31

        [root@devopsage ~]#



###     8. man

* This command shows the manual of the command. It is often called as manual pages or simply man pages. It gives you a  complete information of the command, with all its details, options etc.

        Example: man cal , it will give you every details of the cal command. Output of man command is a complete file with organised details of that perticular command.

        [root@devopsage ~]# man cal   // manual for the cal command

##      9. info

* info command is similar to the man command, it also gives some information about the command passed as an arguments.

        [root@devopsage ~]# info cal
        NAME
        cal, ncal — displays a calendar and the date of Easter

        SYNOPSIS
            cal [-31jy] [-A number] [-B number] [-d yyyy-mm] [[month] year]
            cal [-31j] [-A number] [-B number] [-d yyyy-mm] -m month [year]
            ncal [-C] [-31jy] [-A number] [-B number] [-d yyyy-mm] [[month] year]
            ncal [-C] [-31j] [-A number] [-B number] [-d yyyy-mm] -m month [year]
            ncal [-31bhjJpwySM] [-A number] [-B number] [-H yyyy-mm-dd] [-d yyyy-mm]
                [-s country_code] [[month] year]
            ncal [-31bhJeoSM] [-A number] [-B number] [-d yyyy-mm] [year]

        DESCRIPTION
            The cal utility displays a simple calendar in traditional format and ncal
            offers an alternative layout, more options and the date of Easter.  The
            new format is a little cramped but it makes a year fit on a 25x80 termi‐
            nal.  If arguments are not specified, the current month is displayed.

            The options are as follows:

            -h      Turns off highlighting of today.

            -J      Display Julian Calendar, if combined with the -o option, display
                    date of Orthodox Easter according to the Julian Calendar.

            -e      Display date of Easter (for western churches).

            -j      Display Julian days (days one-based, numbered from January 1).

            -m month
                    Display the specified month.  If month is specified as a decimal
                    number, appending ‘f’ or ‘p’ displays the same month of the fol‐
                    lowing or previous year respectively.


##      10. whatis

* This command will give you short information about the command used as an argument

        Example:

        [root@devopsage ~]# whatis cal
        cal (1)              - display a calendar
        [root@devopsage ~]#