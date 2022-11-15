# Wireshark twoo twooo two twoo...

#### Description
Can you find the flag? [shark2.pcapng](https://mercury.picoctf.net/static/7b8e53329b34946177a9b5f2860a0292/shark2.pcapng).

## Accesos
Did you really find _the_ flag?
Look for traffic that seems suspicious.

## Solucion
filtramos los dns que aparecen en la captura de datos
dns && ip.dst == 18.217.1.57 && dns.qry.name contains local
y los exportamos como csv
```bash
┌──(yareds45㉿yareds45)-[~/develop]
└─$ ls
shark2.pcapng
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ ls
data.csv  datos  shark2.pcapng
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat data.csv 
"No.","Time","Source","Destination","Protocol","Length","Info"
"1637","9.440363","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x1dd2 A cGljb0NU.reddshrimpandherring.com.windomain.local"
"2046","11.972605","192.168.38.104","18.217.1.57","DNS","109","Standard query 0xabb9 A RntkbnNf.reddshrimpandherring.com.windomain.local"
"2448","14.605726","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x9e21 A M3hmMWxf.reddshrimpandherring.com.windomain.local"
"3153","16.506492","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x2ee1 A ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
"3442","18.340155","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x2a4b A YWRiZWVm.reddshrimpandherring.com.windomain.local"
"3982","20.369626","192.168.38.104","18.217.1.57","DNS","105","Standard query 0x4068 A fQ==.reddshrimpandherring.com.windomain.local"
"4374","22.583745","192.168.38.104","18.217.1.57","DNS","105","Standard query 0x7418 A fQ==.reddshrimpandherring.com.windomain.local"
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ nano datos 
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ nano data.csv 
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat data.csv | cut -d ' ' -f 5
cGljb0NU.reddshrimpandherring.com.windomain.local"
RntkbnNf.reddshrimpandherring.com.windomain.local"
M3hmMWxf.reddshrimpandherring.com.windomain.local"
ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
YWRiZWVm.reddshrimpandherring.com.windomain.local"
fQ==.reddshrimpandherring.com.windomain.local"

                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat data.csv | cut -d ' ' -f 5 | cut -d '.' -f1
cGljb0NU
RntkbnNf
M3hmMWxf
ZnR3X2Rl
YWRiZWVm
fQ==

                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat data.csv | cut -d ' ' -f 5 | cut -d '.' -f1 | tr -d '\n'
cGljb0NURntkbnNfM3hmMWxfZnR3X2RlYWRiZWVmfQ==                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat data.csv | cut -d ' ' -f 5 | cut -d '.' -f1 | tr -d '\n' | base64 -d
picoCTF{dns_3xf1l_ftw_deadbeef}   

```


## Referencias