# Level 25 -> 26

## Objetivo
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

## Datos de acceso
ssh bandit25@**bandit.labs.overthewire.org** -p2220

user: bandit25
pass: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solucion 
- [Pasos en terminal]

- [1.-] ls -la

- [2.-] ssh -i bandit26.sshkey bandit26@localhost  -p 2220
- [3.-] ventana pequea de more

- v modo edicion
- ESC :e /etc/bandit_pass/bandit26
- ESC :q salir

c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
