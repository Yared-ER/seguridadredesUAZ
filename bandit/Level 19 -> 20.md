# Level 19 -> 20

## Objetivo
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Datos de acceso
ssh bandit19@**bandit.labs.overthewire.org** -p2220

user: bandit19
pass: awhqfNnAbc1naukrpqDYcF95h7HoMTrC

## Solucion 
```console
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ id
uid=11019(bandit19) gid=11019(bandit19) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do 
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20 
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```