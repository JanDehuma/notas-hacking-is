# shark on wire 2
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.


#### Hints
- (None)


### Solution
```bash
  GNU nano 6.4                                                      shark.py                                                               
from scapy.all import *
packets = rdpcap('capture.pcap')
flag = ''
for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)
print(flag)
```

```bash
┌──(kali㉿kali)-[~/picoctf/forensic/shark2]
└─$ nano shark.py  
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/shark2]
└─$ python shark.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```