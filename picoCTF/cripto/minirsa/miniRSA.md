# miniRSA

## Description
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext)? Something seems a bit small.

## Accesos
[RSA info](https://simple.wikipedia.org/wiki/RSA_algorithm)


How could having too small an e affect the security of this 2048 bit key?

Make sure you don't lose precision, the numbers are pretty big (besides the e value)


## Solucion
```bash
>>> from Crypto.Util.number import long_to_bytes
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933
>>> root, exact = iroot(c, e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388203708028670029596145277)
>>> exact
True
>>> long_to_bytes(root)
b'picoCTF{n33d_a_lArg3r_e_ccaa7776}'
```


## Refrencia RSA
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
d = e mod inv tn

Encriptar: pow(m,e,n)
c = m ^ e mod n

Desencriptar: pow(c,d,n)
m = c ^ d mod n