# Wireshark doo dooo do doo...

## Description
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/81c7862241faf4a48bd64a858392c92b/shark1.pcapng).


## Solucion
Abrir wirechark el paquete de datos
seguir los streams TCP
en el stream 5 al final viene una linea parecida a la bandera
y la rotamos con rot13

Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}

```bash
┌──(yareds45㉿yareds45)-[~/develop]
└─$ echo Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs} | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The flag is picoCTF{p33kab00_1_s33_u_deadbeef}

```


## Referencias