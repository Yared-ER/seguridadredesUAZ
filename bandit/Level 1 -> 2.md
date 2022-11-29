# Level 1-> 2

## Objetivo
The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso
ssh bandit1@**bandit.labs.overthewire.org** -p2220

User: bandit1
Pass: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

## Solucion 
```console
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
bandit1@bandit:~$ 
```
# Referencias 