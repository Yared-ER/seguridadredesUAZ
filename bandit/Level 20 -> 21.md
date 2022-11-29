# Level 20 -> 21

## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## Datos de acceso
ssh bandit20@**bandit.labs.overthewire.org** -p2220

user: bandit20
pass: VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solucion 
```console
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 3873540
bandit20@bandit:~$ Listening on 0.0.0.0 3030

bandit20@bandit:~$ jobs
[1]+  Running                 nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ ./suconnect 3030
Connection received on 127.0.0.1 51392
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
[NvEJF7oVjkddltPSrdKEFOllh9V1IBcq]
[1]+  Done                    nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT

```