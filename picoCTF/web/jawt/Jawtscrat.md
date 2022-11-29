# JaWT Scratchpad

## Descripcion
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090

## Accesos
What is that cookie?
Have you heard of JWT?

## Solucion
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiZmVyIn0.wufhGmDSJBd1ugYI4JLDndi6P-42nLnDZF-nTH47xWA


jwt encriptado con nuestro usuario lo desencriptamos con json y la lista de palabras de linux guardando la firma en un archivo, habiendo encontrado la palabra 
ilovepico
Modificamos el JWT con admin y la palabra ilovepico en la firma
Modificamos la cookie con la nueva palabra en la firma y refrescamos el sitio
el cual entrara con admin y nos entregara la bandera.

tocken
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s

palabra
ilovepico

flag
picoCTF{jawt_was_just_what_you_thought_f859ab2f}



## Links 
https://jwt.io/

https://github.com/openwall/john