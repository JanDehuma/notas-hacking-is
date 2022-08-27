# Bandit

## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Datos de acceso
bandit8
cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Solución 
```bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -c | grep '^ *1'
      1 UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
bandit8@bandit:~$
```

## Notas adicionales

## Referencias
