Ps-dock
=======

Very simple and uncrashable process monitoring tool

Installation
------------
It can be installed with npm.

    npm install ps-dock -g
  
#Usage
###Basic
Ps-dock can launch a process very simply, in this way:

    ps-dock ls --stdout test.log
###Config
Config file can be specified in this way :

    ps-dock bash --stdout test.log --config-file /home/config
By default, ps-dock will search for a file name .psdockrc in current home or current directory. To specify an other directory, you can use --config option:

    ps-dock bash --stdout test.log --config /home
###Stdout
Three types of stdout can be specified :

* 
Logfile

For instance, you can specify a file name test.log to ps-dock. then it handles logrotation : by defaults, log files are rotated every day, but you can tell to ps-dock to rotate logs every second, every minute, every hour, every day, or every week in this way:
    
    ps-dock bash --stdout test.log --log-rotate hourly

* 
TCP Socket

A distant socket to which send datas from process. Process input is plugged to this socket...

    ps-dock bash --stdout socket://localhost:666
Data can be sent on connection to the distant socket in this way:

    ps-dock bash --stdout socket://localhost:666/"hello world!"
    
*TLS Socket

    ps-dock bash --stdout tls://localhost:666