# Level 27 -> 28

## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Datos de acceso
ssh bandit27@**bandit.labs.overthewire.org** -p2220

user: bandit27
pass: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solucion 
```console
bandit27@bandit:~$ mkdir /tmp/fergit
bandit27@bandit:~$ cd /tmp/fergit
bandit27@bandit:/tmp/fergit$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/fergit$ cd repo
bandit27@bandit:/tmp/fergit/repo$ ls -la
total 16
drwxrwxr-x 3 bandit27 bandit27 4096 Sep  6 14:30 .
drwxrwxr-x 3 bandit27 bandit27 4096 Sep  6 14:30 ..
drwxrwxr-x 8 bandit27 bandit27 4096 Sep  6 14:30 .git
-rw-rw-r-- 1 bandit27 bandit27   68 Sep  6 14:30 README
bandit27@bandit:/tmp/fergit/repo$ cat README 
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```