# WebNet0
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

#### Hints
- Try using a tool like Wireshark.
- How can you decrypt the TLS stream?

### Solution
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/shark]
└─$ ls
capture.pcap  picopico.key

┌──(kali㉿kali)-[~/picoctf/forensic/shark]
└─$ wireshark capture.pcap                                                                          

┌──(kali㉿kali)-[~/picoctf/forensic/shark]
└─$ wireshark capture.pcap
 ** (wireshark:17805) 12:27:49.713000 [GUI WARNING] -- FIX Add drag reordering to UAT dialog
```
![[Pasted image 20221018122915.png]]
picoCTF{nongshim.shrimp.crackers}


