# c0rrupt
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

#### Hints
Try fixing the file header

### Solution
```bash
──(kali㉿kali)-[~/picoctf/forensic/corrupt]
└─$ ls
mystery  reparada.png

┌──(kali㉿kali)-[~/picoctf/forensic/corrupt]
└─$ hexeditor reparada.png

┌──(kali㉿kali)-[~/picoctf/forensic/corrupt]
└─$ open reparada.png    

┌──(kali㉿kali)-[~/picoctf/forensic/corrupt]
└─$ 
```

![[Pasted image 20221018122015.png]]
picoCTF{c0rrut10n_1847995}

