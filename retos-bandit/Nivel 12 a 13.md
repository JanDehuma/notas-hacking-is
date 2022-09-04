# Bandit

## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso
bandit12
5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

## Solución 
```bash
bandit12@bandit:~$ bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO |zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO |zcat
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
bandit12@bandit:~$
```

## Notas adicionales

## Referencias
https://joseblanco.pro/tipos-de-empaquetado-y-compresion-de-archivos-en-linux/
