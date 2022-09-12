# Bandit

## Objetivo
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

## Datos de acceso
bandit25
uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG

## Solución 
```bash
bandit25@bandit:~$ ls  
bandit26.sshkey  
bandit25@bandit:~$
bandit25@bandit:~$ ssh bandit26@localhost -i bandit26.sshkey
bandit25@bandit:~$ cat /etc/passwd | grep bandit26  
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext  
bandit25@bandit:~$
bandit25@bandit:~$ cat /usr/bin/showtext  
#!/bin/shexport TERM=linuxmore ~/text.txt  
exit 0  
bandit25@bandit:~$
:e /etc/bandit_pass/bandit26
:set shell=/bin/bash
_5czgV9L3Xx8JPOyRbXh6lQbmIOWvPT6Z_
```

## Notas adicionales

## Referencias