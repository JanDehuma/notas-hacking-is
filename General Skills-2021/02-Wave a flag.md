# Wave a flag
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm) has extraordinarily helpful information...

#### Hints
- This program will only work in the webshell or another Linux computer.
- To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm`
- Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
- -h and --help are the most common arguments to give to programs to get more information from them!
- Not every program implements help features like -h and --help.

##Solucion
```bash
──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm
--2022-09-13 10:27:14--  https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: ‘warm’

warm                100%[================>]  10.68K  --.-KB/s    in 0s      

2022-09-13 10:27:15 (74.6 MB/s) - ‘warm’ saved [10936/10936]

                                                                             
┌──(kali㉿kali)-[~]
└─$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=7b3da2efd83a2b9154697b6c7f6474042e1fd033, with debug_info, not stripped
                                                                             
┌──(kali㉿kali)-[~]
└─$ chmod +x warm
                                                                             
┌──(kali㉿kali)-[~]
└─$ ./warm
Hello user! Pass me a -h to learn what I can do!
                                                                             
┌──(kali㉿kali)-[~]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
                                                                             
┌──(kali㉿kali)-[~]
└─$ 

```

[[03-Nice netcat...]]