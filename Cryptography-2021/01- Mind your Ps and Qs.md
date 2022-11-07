# Mind your Ps and Qs
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)

#### Hints
- Bits are expensive, I used only a little bit over 100 to save money

### Solution
```bash

┌──(kali㉿kali)-[~/picoctf/crypto]
└─$ wget https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values
--2022-10-25 09:23:16--  https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 205 [application/octet-stream]
Saving to: ‘values’

values                             100%[===============================================================>]     205  --.-KB/s    in 0s      

2022-10-25 09:23:16 (415 MB/s) - ‘values’ saved [205/205]


┌──(kali㉿kali)-[~/picoctf/crypto]
└─$ ls                                               
values

┌──(kali㉿kali)-[~/picoctf/crypto]
└─$ cat values                                       
Decrypt my super sick RSA:
c: 421345306292040663864066688931456845278496274597031632020995583473619804626233684
n: 631371953793368771804570727896887140714495090919073481680274581226742748040342637
e: 65537                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/crypto]
└─$ 

┌──(kali㉿kali)-[~]
└─$ cd RsaCtfTool

┌──(kali㉿kali)-[~/RsaCtfTool]
└─$ python3 RsaCtfTool.py -n 631371953793368771804570727896887140714495090919073481680274581226742748040342637 -e 65537 --uncipher 421345306292040663864066688931456845278496274597031632020995583473619804626233684
private argument is not set, the private key will not be displayed, even if recovered.

[*] Testing key /tmp/tmpw17y5cxk.
attack initialized...
[*] Performing smallq attack on /tmp/tmpw17y5cxk.
[*] Performing factordb attack on /tmp/tmpw17y5cxk.
[*] Attack success with factordb method !

Results for /tmp/tmpw17y5cxk:

Unciphered data :
HEX : 0x7069636f4354467b736d6131315f4e5f6e305f67306f645f35353330343539347d
INT (big endian) : 13016382529449106065927291425342535437996222135352905256639647889241102700065917
INT (little endian) : 14497632500273096310326224574698701586593423286297521113119707573529906094762352
utf-8 : picoCTF{sma11_N_n0_g0od_55304594}
STR : b'picoCTF{sma11_N_n0_g0od_55304594}'
HEX : 0x007069636f4354467b736d6131315f4e5f6e305f67306f645f35353330343539347d
INT (big endian) : 13016382529449106065927291425342535437996222135352905256639647889241102700065917
INT (little endian) : 3711393920069912655443513491122867606167916361292165404958645138823655960259162112
utf-8 : picoCTF{sma11_N_n0_g0od_55304594}
utf-16 : 瀀捩䍯䙔獻慭ㄱ也湟弰で摯㕟㌵㐰㤵紴
STR : b'\x00picoCTF{sma11_N_n0_g0od_55304594}'

┌──(kali㉿kali)-[~/RsaCtfTool]
└─$ 
```