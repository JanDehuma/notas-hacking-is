# Sleuthkit Intro
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

-   [Download disk image](https://artifacts.picoctf.net/c/114/disk.img.gz)
-   Access checker program: `nc saturn.picoctf.net 52279`

#### Hints
(None)

### Solution
```bash
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ ls
disk.img.gz
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ ls -la
total 29028
drwxr-xr-x 2 kali kali     4096 Oct 13 10:26 .
drwxr-xr-x 4 kali kali     4096 Oct 13 10:26 ..
-rw-r--r-- 1 kali kali 29714372 Mar 15  2022 disk.img.gz
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ gzip -d disk.img.gz 
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ ls -la
total 102408
drwxr-xr-x 2 kali kali      4096 Oct 13 10:27 .
drwxr-xr-x 4 kali kali      4096 Oct 13 10:26 ..
-rw-r--r-- 1 kali kali 104857600 Mar 15  2022 disk.img
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ ls -lah
total 101M
drwxr-xr-x 2 kali kali 4.0K Oct 13 10:27 .
drwxr-xr-x 4 kali kali 4.0K Oct 13 10:26 ..
-rw-r--r-- 1 kali kali 100M Mar 15  2022 disk.img
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ file disk.img     
disk.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0xc,190,50), startsector 2048, 202752 sectors
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ mmls -V disk.img  
The Sleuth Kit ver 4.11.1
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ mmls disk.img  
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ nc saturn.picoctf.net 52279
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic2022]
└─$ 

```