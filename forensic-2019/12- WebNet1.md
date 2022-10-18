# WebNet1
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

#### Hints
- Try using a tool like Wireshark.
- How can you decrypt the TLS stream?

### Solution
``` bash
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/web1]
└─$ ls
capture.pcap  picopico.key
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/web1]
└─$ wireshark capture.pcap                                                                          
 ** (wireshark:19415) 12:33:26.780513 [GUI WARNING] -- FIX Add drag reordering to UAT dialog
^C
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/web1]
└─$ LS
LS: command not found
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/web1]
└─$ ls
capture.pcap  favicon.ico  picopico.key  second.html  starter-template.css  vulture.jpg

┌──(kali㉿kali)-[~/picoctf/forensic/web1]
└─$ open second.html 

┌──(kali㉿kali)-[~/picoctf/forensic/web1]
└─$ strin                                              
Command 'strin' not found, did you mean:
  command 'strip' from deb binutils
Try: sudo apt install <deb name>

┌──(kali㉿kali)-[~/picoctf/forensic/web1]
└─$ strings vulture.jpg -n15             
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz

┌──(kali㉿kali)-[~/picoctf/forensic/web1]
└─$ 

```
