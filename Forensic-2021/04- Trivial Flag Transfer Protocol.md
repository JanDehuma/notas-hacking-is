# Trivial Flag Transfer Protocol
Figure out how they moved the [flag](https://mercury.picoctf.net/static/ed308d382ae6bcc37a5ebc701a1cc4f4/tftp.pcapng).

#### Hints
What are some other ways to hide data?

### Solution


```bash
┌──(kali㉿kali)-[~/picoctf/forensic/tftp]
└─$ steghide --extract -sf picture3.bmp -p DUEDILIGENCE
wrote extracted data to "flag.txt".
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/tftp]
└─$ cat flag.txt                
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/tftp]
└─$ 

```