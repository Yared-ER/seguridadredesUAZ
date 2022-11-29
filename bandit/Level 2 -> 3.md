# Level 2 -> 3

## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Datos de acceso
ssh bandit2@**bandit.labs.overthewire.org** -p2220

user: bandit2
pass: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

# Solucion 
```console
bandit2@bandit:~$ nano 'spaces in this filename' 
Unable to create directory /home/bandit2/.nano: Permission denied
It is required for saving/loading search history or cursor positions.

Press Enter to continue

bandit2@bandit:~$ 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```