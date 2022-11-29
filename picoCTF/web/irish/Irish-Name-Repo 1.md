#  Irish-Name-Repo 1

## Descripcion
There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!

## Accesos
There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?

Try to think about how the website verifies your login.

## Solucion
## Pasos a seguir

Con el ispector vemos el campo oculto y cambiamos el valor a 1
para poder ver la consulta SQL

username: admin 
password: ' or 1=1;
SQL query: SELECT * FROM users WHERE name='admin ' AND password='' or 1=1;'

Your flag is: picoCTF{s0m3_SQL_f8adf3fb}