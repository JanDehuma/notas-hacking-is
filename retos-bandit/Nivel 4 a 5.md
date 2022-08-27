# Bandit

## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

## Datos de acceso
bandit4
pIwrPrtPN36QITSp3EQaw936yaFoFgAB

## Solución 
```bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ find inhere
inhere
inhere/-file01
inhere/-file00
inhere/-file06
inhere/-file03
inhere/-file05
inhere/-file08
inhere/-file04
inhere/-file07
inhere/-file02
inhere/-file09
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file ./-file*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat './-file07'
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
bandit4@bandit:~/inhere$
```

## Notas adicionales

## Referencias