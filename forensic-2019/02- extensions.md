# extensions
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

#### Hints
- How do operating systems know what kind of file it is? (It's not just the ending!
- Make sure to submit the flag as picoCTF{XXXXX}


### Solution
```bash
─(kali㉿kali)-[~/picoctf/forensic]
└─$ file flag.txt    
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ mv flag.txt flag.png
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ open flag.png  


```

