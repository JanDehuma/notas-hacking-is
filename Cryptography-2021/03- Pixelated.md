# Pixelated
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)

#### Hints
- [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
- Think of different ways you can "stack" images

### Solution
```bash
┌──(kali㉿kali)-[~]
└─$ cd /opt/                      
                                                                                                                                           
┌──(kali㉿kali)-[/opt]
└─$ wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
stegsolve.jar: Permission denied
                                                                                                                                           
┌──(kali㉿kali)-[/opt]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar     
[sudo] password for kali: 
--2022-10-25 10:06:42--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.173.1
Connecting to www.caesum.com (www.caesum.com)|216.234.173.1|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar                      100%[===============================================================>] 304.95K  86.1KB/s    in 3.5s    

2022-10-25 10:06:46 (86.1 KB/s) - ‘stegsolve.jar’ saved [312271/312271]

                                                                                                                                           
┌──(kali㉿kali)-[/opt]
└─$ chmod +x stegsolve.jar
chmod: changing permissions of 'stegsolve.jar': Operation not permitted
                                                                                                                                           
┌──(kali㉿kali)-[/opt]
└─$ ls
microsoft  sstv  stegsolve.jar
                                                                                                                                           
┌──(kali㉿kali)-[/opt]
└─$ sudo chmod +x stegsolve.jar                                            
                                                                                                                                           
┌──(kali㉿kali)-[/opt]
└─$ 

                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]
└─$ ls
scrambled1.png  scrambled2.png
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]
└─$ java -jar /opt/stegsolve.jar                 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

```

picoCTF{d562333d}