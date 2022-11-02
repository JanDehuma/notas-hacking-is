Decrypt this [message](https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext).

#### Hints
- caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

### Solution
```bash
┌──(kali㉿kali)-[~/picoctf/cripto/cesar]
└─$ ls
ciphertext

┌──(kali㉿kali)-[~/picoctf/cripto/cesar]
└─$ cat ciphertext                                                                    
picoCTF{dspttjohuifsvcjdpoabrkttds}  

┌──(kali㉿kali)-[~/picoctf/cripto/cesar]
└─$ nano exp.py   

──(kali㉿kali)-[~/picoctf/cripto/cesar]
└─$ python3 exp.py
crossingtherubiconzaqjsscr

```