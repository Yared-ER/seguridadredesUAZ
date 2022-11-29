# Level 9  -> 10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso
ssh bandit9@**bandit.labs.overthewire.org** -p2220

user: bandit9
pass: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

# Solucion 
```console
bandit9@bandit:~$ cat  data.txt  | strings | grep ==
========== the
bu========== password
4iu========== is
b~==P
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```