# Level 16 -> 17

## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de acceso
ssh bandit16@**bandit.labs.overthewire.org** -p2220

user: bandit16
pass: JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solucion 
```console
nmap localhost -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2022-09-04 06:15 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00017s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.05 seconds

bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  3 23:40:42 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  3 23:40:42 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  3 23:39:42 2022 GMT; NotAfter: Sep  3 23:40:42 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEPBAeDzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTAzMjMzOTQyWhcNMjIwOTAzMjM0MDQyWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDJ
oaGloiCj5rvCVLShjf7nTU9pTzioKE5KGG7ac3eq6yO+3wHqMTwCFvqrNB4ZjcLD
Kbttx2enLnHU3ncVxb42sf+vez3L6nfnXYcEyRRB2Cmq5ndVxhDCfMXd0jQVkzF+
388rJNbfEr5xSR7YznfHllQLGLV08G92mmjsPv7+adPyEZ5M6/2gC8OdOmr3J1lE
CD9M7DcYz9zeAZ5ri0l7IF/hghbiuRNVywVFe9jRLCoaGs1a4eWvUe4qwAvuZ9Dt
38Fix1XaaHZK6BOUkelh7lP/ZDQdEck2W7/8V+hHR0cd7ZJb7Emn8WdaXf04786b
n721Grcm2HXIbpZaAHrNAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCK
REInXE2/tbk1lkCo8B/79Ckpq3sX/gHB+Q8aXuQNqlTTTUMwiHRdnnuC2imoqoq9
dHYOuhWpAoqKhAyezQkj7WtTjTXfT8ViNWzxPQcPUki1ERlQIRgZc/IGgW6jbzzg
PEfJiuIKr56lC/zFQkL7L9iusSopSGQGvz8rJz9YsOIHDycWhFQaJFFnpySQJOp1
RjSfZvKWuWloSCxyLrp0RdAWHpfshUh3UZQxqP5NzbNR6hCXh5o/1WqCS9RHkviS
LY3tn2wUJPX2DexmpAh+NzfimKN4UMKijnvmIRNF1Kd6TEidT8cZRvXnUnNkm/qg
LzdmlimtXnifHPGCsmXp
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 8EC3C1BD8BDC9769AE1B550C382F70AB867421E735CFEB91F710D3338B0C008E
    Session-ID-ctx: 
    Resumption PSK: F29F0F49819AD8946E10092DC516621B2AEE1A40DC752A440A95FA340DB4C05F0235038286DE8FBF840CA682B6111894
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fb 34 dc b1 cc 2b c6 d3-52 56 11 ae 76 76 80 c3   .4...+..RV..vv..
    0010 - 7f b9 9c 9a 89 04 fe 55-fd bb 92 30 0b c6 0a 80   .......U...0....
    0020 - 69 70 00 10 6c ad 34 79-06 d6 92 7f f5 23 f1 60   ip..l.4y.....#.`
    0030 - 24 dd 32 4b 2c a6 13 a3-61 23 eb 0a 0d 15 b8 de   $.2K,...a#......
    0040 - 26 56 c7 0e a3 f7 76 8f-55 b9 67 ca 2c b8 a6 14   &V....v.U.g.,...
    0050 - 2c 96 73 7a 07 1f 38 8e-c8 52 b2 77 8d 51 d9 c4   ,.sz..8..R.w.Q..
    0060 - 43 f8 59 1e 54 3c db 60-56 89 f9 50 0e 64 28 18   C.Y.T<.`V..P.d(.
    0070 - 16 ba 9f 7e e2 4a 93 63-59 28 a8 45 b9 87 a2 37   ...~.J.cY(.E...7
    0080 - 3f c4 0c e6 cf eb 30 57-19 eb b3 c3 e6 fd 15 b4   ?.....0W........
    0090 - 85 39 58 18 5a f5 37 60-8b 41 89 4c 11 43 1f da   .9X.Z.7`.A.L.C..
    00a0 - 4f 5d e6 f5 c8 4c 1b bb-57 f0 19 53 bf 47 a6 b1   O]...L..W..S.G..
    00b0 - 38 f7 b9 db b4 dd ea 8f-de 05 9d a7 1d 6a 87 4c   8............j.L
    00c0 - 62 19 28 5b 4d 06 6b d0-b5 6c 8e 81 bb 9b 54 c0   b.([M.k..l....T.

    Start Time: 1662272214
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 370D82BB7371FFE6DFE63F040339B766C2D7A193EF926CCE6F0616A2A69C8B80
    Session-ID-ctx: 
    Resumption PSK: B8FF8A7B2C6BB1D86E6623BA70598027A6E61675CA04BB6D5317E9EF523A22FD09C6D8D10C622EEC05276C536A46A5EA
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fb 34 dc b1 cc 2b c6 d3-52 56 11 ae 76 76 80 c3   .4...+..RV..vv..
    0010 - d6 d4 3a 97 45 c1 8e 3e-36 62 47 2e d4 38 41 1b   ..:.E..>6bG..8A.
    0020 - 02 37 43 b9 b9 a4 4d 49-ff 4e 49 cc cf 54 ab a8   .7C...MI.NI..T..
    0030 - 7f 2d 6e b1 60 05 e6 0e-1a 00 67 9a f9 8e 0e 19   .-n.`.....g.....
    0040 - c5 3a 5e f0 bb 6a db f2-56 dd 27 d6 56 bf 30 13   .:^..j..V.'.V.0.
    0050 - 43 b8 82 a8 d2 ae d1 80-be 19 77 3a 11 c7 cf f6   C.........w:....
    0060 - 10 2c 5a 4f 9d 50 34 0d-cc 81 40 16 eb ec bd 87   .,ZO.P4...@.....
    0070 - 9d ae 54 8e ec f9 42 d0-22 e1 d0 73 0b 4f 2e e3   ..T...B."..s.O..
    0080 - d3 2d 89 bf 21 10 b7 3a-a8 1c a6 ca 15 cb c8 94   .-..!..:........
    0090 - 81 3c 5b 12 b4 eb 23 c4-de 54 ce 44 9f 5f 25 ce   .<[...#..T.D._%.
    00a0 - 74 88 88 f8 69 75 90 f3-a4 f8 ef 30 ee 2a 7f 2e   t...iu.....0.*..
    00b0 - 62 33 0d 6e 61 22 c4 24-01 42 87 1f c9 c8 60 e7   b3.na".$.B....`.
    00c0 - e8 42 f8 cb 48 d8 a1 8e-ed 1a 65 38 10 3a 05 a3   .B..H.....e8.:..

    Start Time: 1662272214
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---

read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed

bandit16@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
```console                                                                                
┌──(yareds45㉿yareds45)-[~]
└─$ nano llave17

## Paso 5 
┌──(yareds45㉿yareds45)-[~]
└─$ chmod 600 llave17

```
```console
bandit17@bandit:~$ cat /etc/bandit_pass/bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
```as 