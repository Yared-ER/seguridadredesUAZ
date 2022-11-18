# information

#### Description
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values)

## Accesos
Bits are expensive, I used only a little bit over 100 to save money


## Solucion
Factorizar n en la pagina factorDB y nos dara p y q

```bash
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat values         
Decrypt my super sick RSA:
c: 861270243527190895777142537838333832920579264010533029282104230006461420086153423
n: 1311097532562595991877980619849724606784164430105441327897358800116889057763413423
e: 65537  


┌──(yareds45㉿yareds45)-[~/develop]
└─$ python3        
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c = 861270243527190895777142537838333832920579264010533029282104230006461420086153423
>>> e = 65537
>>> p = 1955175890537890492055221842734816092141
>>> q = 670577792467509699665091201633524389157003
>>> n = p * q
>>> tn = (p-1) * (q-1)
>>> d = inverse(e,tn)
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639573959002849415739773
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_13686679}'

```


## Referencias
http://factordb.com/


P - numero primo
Q - numero primo
N - modulo
tn - totient n
E - exponente (llave publica) - 65337
D - llave privada
C - mensaje cifrado
M - mensaje en texto plano

n = p * q
tn = (p-1) * (q-1)
d = e mod inv tn      //  inverse(e,tn)

Encriptar: pow(m,e,n)
c = m ^ e mod n

Desencriptar: pow(c,d,n)
m = c ^ d mod n