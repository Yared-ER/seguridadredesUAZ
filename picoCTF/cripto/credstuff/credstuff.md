# credstuff

#### Description
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/534/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

## Accesos
Maybe other passwords will have hints about the leak?


## Solucion

```bash
┌──(yareds45㉿yareds45)-[~/develop]
└─$ tar -xvf leak.tar 
leak/
leak/passwords.txt
leak/usernames.txt

┌──(yareds45㉿yareds45)-[~/develop]
└─$ ls
leak  leak.tar
┌──(yareds45㉿yareds45)-[~/develop]
└─$ ls
passwords.txt  usernames.txt

┌──(yareds45㉿yareds45)-[~/develop]
└─$ nvim usernames.txt
:/`cultiris` linea 378

┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat passwords.txt | head -n 378 | tail -n 1
cvpbPGS{P7e1S_54I35_71Z3}


┌──(yareds45㉿yareds45)-[~/develop]
└─$ echo ‘cvpbPGS{P7e1S_54I35_71Z3}’ | tr 'A-Za-z' 'N-ZA-Mn-za-m'
‘picoCTF{C7r1F_54V35_71M3}’


```


## Referencias
