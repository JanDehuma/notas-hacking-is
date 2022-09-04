# Bandit

## Objetivo
he password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

## Datos de acceso
bandit18
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Solución 
```bash
C:\Users\Jan Dehuma>ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash
bandit18@bandit.labs.overthewire.org's password:
id
uid=11018(bandit18) gid=11018(bandit18) groups=11018(bandit18)
whoami
bandit18
cat readme18
cat: readme18: No such file or directory
cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

## Notas adicionales

## Referencias