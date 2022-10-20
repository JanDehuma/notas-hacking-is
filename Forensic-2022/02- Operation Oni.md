# Operation Oni
Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

#### Hints
(None)

### Solution
```bash
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ wget https://artifacts.picoctf.net/c/374/disk.img.gz                              
--2022-10-19 22:25:58--  https://artifacts.picoctf.net/c/374/disk.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 99.84.192.2, 99.84.192.11, 99.84.192.79, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|99.84.192.2|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 48132743 (46M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                        100%[===============================================================>]  45.90M  1.20MB/s    in 67s     

2022-10-19 22:27:07 (700 KB/s) - ‘disk.img.gz’ saved [48132743/48132743]

                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ ls
disk.img.gz
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ file disk.img.gz             
disk.img.gz: gzip compressed data, was "disk.img", last modified: Wed Oct  6 14:32:01 2021, from Unix, original size modulo 2^32 241172480
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ gzip -d disk.img.gz            
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ ls
disk.img
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ open disk.img 
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ mmls disk.img     
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ fls -o 206848 disk.img
d/d 458:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ fls -o 206848 disk.img 470
r/r 2344:       .ash_history
d/d 3916:       .ssh
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ fls -o 206848 disk.img 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ icat -o 206848 disk.img 2345
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ icat -o 206848 disk.img 2345 > key_file
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ cat key_file 
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ ls -la 
total 235532
drwxr-xr-x  2 kali kali      4096 Oct 19 22:33 .
drwxr-xr-x 18 kali kali      4096 Oct 19 22:25 ..
-rw-r--r--  1 kali kali 241172480 Mar 15  2022 disk.img
-rw-r--r--  1 kali kali       411 Oct 19 22:33 key_file
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ chmod 400 key_file 
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ ls -la
total 235532
drwxr-xr-x  2 kali kali      4096 Oct 19 22:33 .
drwxr-xr-x 18 kali kali      4096 Oct 19 22:25 ..
-rw-r--r--  1 kali kali 241172480 Mar 15  2022 disk.img
-r--------  1 kali kali       411 Oct 19 22:33 key_file
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ ssh -i key_file -p 59100 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:59100 ([18.217.86.78]:59100)' can't be established.
ED25519 key fingerprint is SHA256:5gIm/EJ9bYnoH4qed83W5HXLfN1DO55849f6Lze0lx8.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added '[saturn.picoctf.net]:59100' (ED25519) to the list of known hosts.
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.13.0-1025-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_af277f77}ctf-player@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/operationoni]
└─$ 

```