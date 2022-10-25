# Redaction gone wrong
Now you DON’T see me. This [report](https://artifacts.picoctf.net/c/264/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

#### Hints
- How can you be sure of the redaction?

### Solution
![[Pasted image 20221024225446.png]]
```bash

┌──(kali㉿kali)-[~/picoctf/forensic/redaction]
└─$ ls                                                                        
Financial_Report_for_ABC_Labs.pdf

┌──(kali㉿kali)-[~/picoctf/forensic/redaction]
└─$ open Financial_Report_for_ABC_Labs.pdf | grep pico

```

picoCTF{C4n_Y0u_S33_m3_fully}