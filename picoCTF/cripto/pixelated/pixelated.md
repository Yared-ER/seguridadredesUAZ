# Pixelated

#### Description
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled2.png)

## Hints
### 1
[https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)

### 2
Think of different ways you can "stack" images


## Solucion

```bash
 ──(yareds45㉿yareds45)-[~/develop]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
[sudo] password for masterfer: 
--2022-10-29 13:53:41--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.173.1
Connecting to www.caesum.com (www.caesum.com)|216.234.173.1|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar           100%[===============================>] 304.95K   233KB/s    in 1.3s    

2022-10-29 13:53:43 (233 KB/s) - ‘stegsolve.jar’ saved [312271/312271]


┌──(yareds45㉿yareds45)-[~/develop]
└─$ sudo chmod +x stegsolve.jar 

┌──(yareds45㉿yareds45)-[~/develop]
└─$ java -jar stegsolve.jar
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true


```
picoCTF{d72ea4af}

## Referencias
https://github.com/zardus/ctf-tools/blob/master/stegsolve/install