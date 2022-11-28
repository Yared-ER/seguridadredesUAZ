# unpackme.py

## Descripcion
Can you get the flag? Reverse engineer this [Python program](https://artifacts.picoctf.net/c/465/unpackme.flag.py).

## Solucion


```python
import base64
from cryptography.fernet import Fernet



payload = b'gAAAAABiMD06eCisTWoohiYL5jHGdCte5LAviTFguZQSIyRLAWICJpmdrgxhdTB923h6eksddKpKH41I5-HGzI6xGF_7eb_1u0S2Phw2NvYGTF>'

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
print(plain.decode()) AGREGAMOS ESTA LINEA
exec(plain.decode())
```

```console
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ python3 unpackme.flag.py

pw = input('What\'s the password? ')

if pw == 'batteryhorse':
  print('picoCTF{175_chr157m45_cd82f94c}')
else:
  print('That password is incorrect.')


What's the password? 


```
picoCTF{175_chr157m45_cd82f94c}


## Referencias
