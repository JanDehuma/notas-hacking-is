# basic-mod1
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/395/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

#### Hints
- Do you know what `mod 37` means?
- `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

### Solution
Python
```bash
  GNU nano 6.4                                                       exp.py                                                                
print(datos)

for n in datos:
        if n in range(26):
                flag += chr(n+65)
        elif n in range(26,36):
                flag += chr(n+22)
        else:
                flag += "_"

print(flag)

```

Terminal
```bash
┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]
└─$ python exp.py

┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]
└─$ python exp.py
[17, 26, 20, 13, 3, 36, 13, 36, 17, 26, 20, 13, 3, 36, 0, 3, 3, 27, 33, 4, 2, 28]

┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]
└─$ python exp.py
[17, 26, 20, 13, 3, 36, 13, 36, 17, 26, 20, 13, 3, 36, 0, 3, 3, 27, 33, 4, 2, 28]
RUNDNRUNDADDEC

┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]
└─$ python exp.py
[17, 26, 20, 13, 3, 36, 13, 36, 17, 26, 20, 13, 3, 36, 0, 3, 3, 27, 33, 4, 2, 28]
R0UNDNR0UNDADD17EC2

┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]
└─$ python exp.py
[17, 26, 20, 13, 3, 36, 13, 36, 17, 26, 20, 13, 3, 36, 0, 3, 3, 27, 33, 4, 2, 28]
R0UND_N_R0UND_ADD17EC2

```

picoCTF{R0UND_N_R0UND_ADD17EC2}