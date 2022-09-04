# Bandit

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

## Datos de acceso
bandit15
BfMYroe26WYalil77FoDi9qh59eK5xNr

## Solución 
```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
BfMYroe26WYalil77FoDi9qh59eK5xNr
Correct!
cluFn7wTiGryunymYOu4RcffSxQluehd
```

## Notas adicionales

## Referencias