# Bandit

## Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

## Datos de acceso
bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
## Solución 
```bash
bandit17@bandit:~$ ls  
passwords.new passwords.old  
bandit17@bandit:~$ diff passwords.new passwords.old  
42c42  
< **kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd**  
---  
> hlbSBPAWJmL6WFDb06gpTx1pPButblOA
```

## Notas adicionales

## Referencias
