#  GET aHEAD

## Descripcion
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:34561/](http://mercury.picoctf.net:34561/)

## Accesos
Maybe you have more than 2 choices

Check out tools like Burpsuite to modify your requests and look at the responses

## Solucion

```console
┌──(yareds45㉿yareds45)-[~/develop/web]
└─$ curl -I http://mercury.picoctf.net:34561/index.php
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_8f878508}
Content-type: text/html; charset=UTF-8

         
```

picoCTF{r3j3ct_th3_du4l1ty_8f878508}