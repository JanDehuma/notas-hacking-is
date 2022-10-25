# Packets Primer
Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/200/network-dump.flag.pcap)

#### Hints
- Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.

### Solution
![[Pasted image 20221024224833.png]]
```bash
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/packetsprimer]
└─$ wget https://artifacts.picoctf.net/c/200/network-dump.flag.pcap
--2022-10-24 22:47:44--  https://artifacts.picoctf.net/c/200/network-dump.flag.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 99.84.192.17, 99.84.192.11, 99.84.192.2, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|99.84.192.17|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 778 [application/octet-stream]
Saving to: ‘network-dump.flag.pcap’

network-dump.flag.pcap             100%[===============================================================>]     778  --.-KB/s    in 0s      

2022-10-24 22:47:44 (27.2 MB/s) - ‘network-dump.flag.pcap’ saved [778/778]

                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/packetsprimer]
└─$ ls
network-dump.flag.pcap
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/packetsprimer]
└─$ wireshark network-dump.flag.pcap                               


```

picoCTF{p4ck37_5h4rk_b9d53765}