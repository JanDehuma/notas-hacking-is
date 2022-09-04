# Bandit

## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Datos de acceso
bandit10
truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

## Solución 
```bash
bandit10@bandit:~$ python
Python 2.7.13 (default, Sep 26 2018, 18:42:22)
[GCC 6.3.0 20170516] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> imprt codecs
  File "<stdin>", line 1
    imprt codecs
               ^
SyntaxError: invalid syntax
>>> import codecs
>>> data = open('data.txt', 'r').read()
>>> data
'VGhlIHBhc3N3b3JkIGlzIElGdWt3S0dzRlc4TU9xM0lSRnFyeEUxaHhUTkViVVBSCg==\n'
>>> codecs.decode(data, 'base64')
'The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR\n'
```

## Notas adicionales

## Referencias

