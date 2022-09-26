# Obedient Cat
This file has a flag in plain sight (aka "in-the-clear"). 

#### Hints
- Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.

- To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag`

- `$ man cat`

##Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag
--2022-09-13 10:22:18--  https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: ‘flag’

flag                100%[================>]      34  --.-KB/s    in 0s      

2022-09-13 10:22:18 (46.9 MB/s) - ‘flag’ saved [34/34]

                                                                             
┌──(kali㉿kali)-[~]
└─$ cat flag | grep pico
picoCTF{s4n1ty_v3r1f13d_4a2b35fd}

```

[[02-Wave a flag]]