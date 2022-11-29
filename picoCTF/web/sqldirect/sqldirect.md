# SQL Direct

## Descripcion
Connect to this PostgreSQL server and find the flag!


## Solucion
```console
┌──(yareds45㉿yareds45)-[~/develop/web]
└─$ psql -h saturn.picoctf.net -p 65249 -U postgres pico
Password for user postgres: 
psql (14.4 (Debian 14.4-1+b1), server 14.2 (Debian 14.2-1.pgdg110+1))
Type "help" for help.

pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)
        ^
pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 

```

## referencias
https://www.postgresql.org/