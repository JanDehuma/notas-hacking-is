# Information
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg)

#### Hints
- Look at the details of the file
- Make sure to submit the flag as picoCTF{XXXXX}

### Solution
```bash
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/information]
└─$ ls
cat.jpg
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/information]
└─$ open        
xdg-open - opens a file or URL in the user's preferred application

Synopsis

xdg-open { file | URL }

xdg-open { --help | --manual | --version }

Use 'man xdg-open' or 'xdg-open --manual' for additional info.
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/information]
└─$ open cat.jpg 
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/information]
└─$ exiftool cat.jpg
ExifTool Version Number         : 12.44
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 14:24:46-04:00
File Access Date/Time           : 2022:10:24 22:14:38-04:00
File Inode Change Date/Time     : 2022:10:24 22:14:25-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/forensic/information]
└─$ 

```

![[Pasted image 20221024222307.png]]