# B1ll_Gat35
Can you reverse this [Windows Binary](https://jupiter.challenges.picoctf.org/static/0ef5d0d6d552cd5e0bd60c2adbddaa94/win-exec-1.exe)?

#### Hints
- Microsoft provides windows virtual machines https://developer.microsoft.com/en-us/windows/downloads/virtual-machines
- Ollydbg may be helpful
- Flag format: PICOCTF{XXXX}

### Solution
Dentro de Ghidra buscamos como inicializa el el programa y encontramos que dentro del JNZ hay un if que condiciona el codigo en caso de que se ingreso la llave correcta  y en caso de que la llave sea incorrecta

![[Pasted image 20221115093558.png]]
En la funcion JNZ lo cambiamos a un JNC para que pueda saltarse el if y podamos saltarnos ese paso para acceder a la bandera

```bash
┌──(kali㉿kali)-[~]
└─$ wine win-exec-2.exe.bin                                                                           
Input a number between 1 and 5 digits: 1234
Initializing...
Enter the correct key to get the access codes: 1234
Correct input. Printing flag: PICOCTF{These are the access codes to the vault: 1063340}
```