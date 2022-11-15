# shark on wire 2

#### Description
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Hints
### (None)

## Solucion

Abrimos el paquete en  wireShark
segumos desde el primer stream
notamos que del  32 hay un start
y en  el  60  un  end
nos  vamos a filtrarlos udp.dstport  == 22 
y notamos que todos salen  del puerto  5000 hacia el 22
pero cambia los 3 ultimos del puerto los cuales son la bandera

usamos el lenguaje python para hacer mas facil la conversion de la bandera.

```bash
┌──(yareds45㉿yareds45)-[~/develop]
└─$ python3            
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(112)
'p'
>>> chr(115)
's'
>>> chr(105)
'i'
>>> chr(111)
'o'
>>> chr(67)
'C'
>>> chr(84)
'T'
>>> chr(70)
'F'
>>> 
from scapy.all import *
packets = rdpcap('capture.pcap')

flag = ''
for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)
print(flag)


```


picoCTF{p1LLf3r3d_data_v1a_st3g0}


## Referencias 
