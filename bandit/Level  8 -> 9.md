# Level 8 -> 9

## Descripcion
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Datos de acceso
ssh bandit8@**bandit.labs.overthewire.org** -p2220

user: bandit8
pass: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Solucion 
```console
bandit8@bandit:~$ cat data.txt | sort | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```
EN632PlfYiZbn3PhVK3XOGSlNInNE00t


# Referencias 