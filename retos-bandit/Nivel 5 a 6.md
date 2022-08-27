# Bandit

## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:
-   human-readable
-   1033 bytes in size
-   not executable

## Datos de acceso
bandit5
koReBOKuIDDepwhWk7jZC0RTdopnAYKh

## Solución 
```bash
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ find ./ -type f -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

## Notas adicionales

## Referencias