# Bandit

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de acceso
bandit14
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

## Solución 
```bash
bandit14@bandit:~$  nc -v localhost 30000
localhost [127.0.0.1] 30000 (?) open
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr

bandit14@bandit:~$
```

## Notas adicionales

## Referencias