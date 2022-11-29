# Roboto Sans

## Descripcion
The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:51108/) out.


## Solucion
1.- nos vamos al robots.txt
http://saturn.picoctf.net:51108/robots.txt

```bash
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```
encontramos esto decodificamos las 
lineas despues de la linea que han visto la bandera en code64

2.- esta ruta js/myfile.txt 
3.- encontramos la bandera.

http://saturn.picoctf.net:51108/js/myfile.txt
picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}

## Referencias 
https://www.base64decode.org/