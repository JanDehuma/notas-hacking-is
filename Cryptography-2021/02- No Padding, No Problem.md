# No Padding, No Problem
Oracles can be your best friend, they will decrypt anything, except the flag's ciphertext. How will you break it? Connect with `nc mercury.picoctf.net 10333`.

#### Hints
- What can you do with a different pair of ciphertext and plaintext? What if it is not so different after all...

### Solution
```bash
>>> n = 122018058029318485431133169353806216634995031798912999940774479269170458446583091254269662712252518575536677356355883176879796141094201907161048592073583458210566537478434271925641978458317981946320146174545752061894913662655345179815296925879040896041934230096879610806883244983132756747828729925097871518289
>>> e = 65537
>>> c = 95045284071253770081597174304825444711088352713274038132452279205466848204369059089135151165824677404204981851794402400163470738313300680902261591784821561834939878587970893640613989087800740762134671575085374684056025508416940405703873201320363966046107083178775385641664522892797127801447580437927858494911
>>> x = pow(2,e,n)
>>> x
120350963021146602524655229001793988146980607511726086276973514079620254438090440419989737624908649000965895543305019975845637563992402573667724536438936580878765016689853152696638721241539841186801953001172320200818248907369810712452946246610245538438000449097340024598077162928654183068451944575398622848973
>>
# A partir de aqui el problema no puede resolverse porque no me da la variable completa decifrada abajo adjunto pruebas
```

```bash
                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ nc mercury.picoctf.net 10333
Welcome to the Padding Oracle Challenge
This oracle will take anything you give it and decrypt using RSA. It will not accept the ciphertext with the secret message... Good Luck!


n: 122018058029318485431133169353806216634995031798912999940774479269170458446583091254269662712252518575536677356355883176879796141094201907161048592073583458210566537478434271925641978458317981946320146174545752061894913662655345179815296925879040896041934230096879610806883244983132756747828729925097871518289
e: 65537
ciphertext: 95045284071253770081597174304825444711088352713274038132452279205466848204369059089135151165824677404204981851794402400163470738313300680902261591784821561834939878587970893640613989087800740762134671575085374684056025508416940405703873201320363966046107083178775385641664522892797127801447580437927858494911


Give me ciphertext to decrypt: 120350963021146602524655229001793988146980607511726086276973514079620254438090440419989737624908649000965895543305019975845637563992402573667724536438936580878765016689853152696638721241539841186801953001172320200818248907369810712452946246610245538438000449097340024598077162928654183068451944575398622848973
Here you go: 2
Give me ciphertext to decrypt: 
///AQUI NO ME LO DA COMPLETO
```