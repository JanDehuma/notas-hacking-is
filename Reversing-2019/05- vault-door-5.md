# vault-door-5
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/0a53bf0deaba6919f98d8550c35aa253/VaultDoor5.java)

#### Hints
- You may find an encoder/decoder tool helpful, such as https://encoding.tools/
- Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.

### Solution
```bash
>>> from base64 import b64decode
>>> from urllib.parse import unquote
>>> 
>>> cad = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTMwJTYyJTM5JTM1JTM3JTYzJTM0JTY2"
>>> cad = b64decode(cad)
>>> cad
b'%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%30%62%39%35%37%63%34%66'
>>> 
>>> cad = unquote(cad)
>>> cad
'c0nv3rt1ng_fr0m_ba5e_64_0b957c4f'
>>> 

```

picoCTF{c0nv3rt1ng_fr0m_ba5e_64_0b957c4f}