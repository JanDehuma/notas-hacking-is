# bufa secret
Juan the explororer extracted this file from the site on the last expedition, but it appears to have been **corrupted**. This may be the secret code to open Francisco Villa vault that was found inside the "Cerro de la Bufa" in Zacatecas City. Can you identify what it once was and possibly fix it ? .

On June 23, 1914, this place was the scene of the "La toma de Zacatecas" (1914), where the revolutionary troops of General Francisco Villa defeated the Huertista army, defining the destiny of the nation.


### Solution
```bash
                                                                               
┌──(kali㉿kali)-[~/metaredCTF/forensic]
└─$ xxd -l corrupted.png
                                                                               
┌──(kali㉿kali)-[~/metaredCTF/forensic]
└─$ pngcheck corrupted.png
corrupted.png  this is neither a PNG or JNG image nor a MNG stream
ERROR: corrupted.png
                                                                               
┌──(kali㉿kali)-[~/metaredCTF/forensic]
└─$ hexeditor corrupted.png
                                                                               
┌──(kali㉿kali)-[~/metaredCTF/forensic]
└─$ open corrupted.png
                                                                               
┌──(kali㉿kali)-[~/metaredCTF/forensic]
└─$ 
```

![[Pasted image 20221018210659.png]]

flagMX{you_found_my_secret_vault}