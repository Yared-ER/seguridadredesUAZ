# patchme 

## Descripcion
Can you get the flag? Run this [Python program](https://artifacts.picoctf.net/c/387/patchme.flag.py) in the same directory as this [encrypted flag](https://artifacts.picoctf.net/c/387/flag.txt.enc).


## Solucion


```python
def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "ak98" + \
                   "-=90" + \
                   "adfjhgj321" + \
                   "sleuth9000"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), "utilitarian")
        print(decryption)
        return
    print("That password is incorrect")

```

```bash
ak98-=90adfjhgj321sleuth9000

┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ python3 patchme.flag.py
Please enter correct password for flag: ak98-=90adfjhgj321sleuth9000
Welcome back... your flag, user:
picoCTF{p47ch1ng_l1f3_h4ck_f01eabfa}


```


## Referencias