# Level 7 ->8

## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos de acceso
ssh bandit7@**bandit.labs.overthewire.org** -p2220

user: bandit7
pass: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

## Solucion 
```console
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```