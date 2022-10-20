# MacroHard WeakEdge
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c00c449c3b08daaccacca6f9d5c55d49/Forensics is fun.pptm)

#### Hints
(None)

### Solution
```bash
                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/forensic/macro]
└─$ ls
'[Content_Types].xml'   docProps  'Forensics is fun.pptm'   ppt   _rels
                                                                                                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/forensic/macro]
└─$ cd ppt                    
                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/forensic/macro/ppt]
└─$ ls
presentation.xml  _rels         slideMasters  tableStyles.xml  vbaProject.bin
                                                                             presProps.xml     slideLayouts  slides        theme            viewProps.xml
                                                                                                                                                         
┌──(kali㉿kali)-[~/picoctf/forensic/macro/ppt]
└─$ cd slideMasters 
                                                                                                                            
┌──(kali㉿kali)-[~/…/forensic/macro/ppt/slideMasters]
└─$ ls
hidden  _rels  slideMaster1.xml
                                                                                                                                                           
┌──(kali㉿kali)-[~/…/forensic/macro/ppt/slideMasters]
└─$ cat hidden       
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q                                                                                                                            
┌──(kali㉿kali)-[~/…/forensic/macro/ppt/slideMasters]
└─$ cat hidden | tr -d ' '
ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ                                                                                                                            
┌──(kali㉿kali)-[~/…/forensic/macro/ppt/slideMasters]
└─$ cat hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input
                                                                                                                                                                                      
┌──(kali㉿kali)-[~/…/forensic/macro/ppt/slideMasters]
└─$ 
```