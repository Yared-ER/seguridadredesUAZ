# Search source

## Descripcion
The developer of this website mistakenly left an important artifact in the website source, can you find it? The website is [here](http://saturn.picoctf.net:50761/)

## Accesos
How could you mirror the website on your local machine so you could use more powerful tools for searching?

## Solucion
```console
┌──(yareds45㉿yareds45)-[~/develop/web]
└─$ wget --recursive http://saturn.picoctf.net:50761/
--2022-10-03 21:40:31--  http://saturn.picoctf.net:50761/
Resolving saturn.picoctf.net (saturn.picoctf.net)... 18.217.86.78
Connecting to saturn.picoctf.net (saturn.picoctf.net)|18.217.86.78|:50761... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15920 (16K) [text/html]
Saving to: ‘saturn.picoctf.net:50761/index.html’

saturn.picoctf.net:5076 100%[===============================>]  15.55K  --.-KB/s    in 0.1s  

┌──(yareds45㉿yareds45)-[~/develop/web]
└─$ grep -rho "picoCTF{.*}" saturn.picoctf.net:50761  
picoCTF{1nsp3ti0n_0f_w3bpag3s_ec95fa49}

```