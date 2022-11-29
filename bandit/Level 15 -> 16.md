# Level 15 -> 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso
ssh bandit15@**bandit.labs.overthewire.org** -p2220

user: bandit15
pass: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solucion 
```console
openssl s_client -connect localhost:30001 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  1 06:31:12 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  1 06:31:12 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  1 06:30:12 2022 GMT; NotAfter: Sep  1 06:31:12 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEHn8h8jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTAxMDYzMDEyWhcNMjIwOTAxMDYzMTEyWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDK
u/UD6yArwj259J4o2IVQQGvM/oGVIiYYppFd1jxltmQ03SOUVg+4px+7qOJuCbxA
AH9NCAl55r7v/VDlwGkpu4c2GaqR3zSAlidrtJjrVFZP/QilXdv0uV35N4i30BuT
DdI+FzlYcQx7ztZdtDxp61FTjET4BIcFmSzMQLitpYeeiVcKLXTPnsF8216drWjQ
0Ucb+3RvGgPo/rKPra8/7WYFa8ALdnu2rwP07ndtMDL3iJF9VMuBsr8UuTdsktwa
174QGx0f3RFkcKJ1foxYnSoHvy0BhxVGguMKuinY6cyLELwnjcAp4A2oGI438GnV
whe39ZlCkGved612QLhDAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQDE
2X2mgxYDvujnIAL2Qbs8JnUBFe3lZsRZJbPgko3MZ4lScB5Rbz+vb6q6s0KGGMjh
sKweg4BtG4sQWDIwX2yd4XwJa8rrGWuoA4kgCQ/jJhFZrbCPbDN3sbzX8Tql+epd
oJyQcvLOkWDazRPgx0i4dMXIgUv0kbE+NCvj2waXHldMyjT6GFL2bdv/Xd8ffnXg
wlggJKKIzl0RMp/5z5n1bPMoLVl5HcUG3UzOsTcqcSThTr3JXeWLjaL0qJfAfcw5
V+GM2tGTQB3c4jvISAl5RAARpvFUMc4d4hKd6aesRcFHZfbtSjxglPFmeL1VGxJ9
EIg5c/xwHOE6dgDA2WdS
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
    Session-ID: 391F54D0CA3E3BD611F312A944A43C5405D11FACBBBF9511D0CC4550F17B8956
    Session-ID-ctx: 
    Resumption PSK: 2E7D6B93126804F3E7E606B347A15EFFE2F689405B1A30C5DF42588C57830FA19389CFE77C664D5577378E3E7C533F6C
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 09 86 a0 aa 25 48 38 1d-0e b1 8d f8 fa 82 ac 33   ....%H8........3
    0010 - fc d6 93 9f 38 14 0c ac-44 6e 57 38 4b 06 7a b5   ....8...DnW8K.z.
    0020 - c3 1a 72 61 a0 a9 f9 11-88 7f 77 23 87 88 8d c9   ..ra......w#....
    0030 - 88 b5 73 de af 36 f2 d8-3f 4a 9a 72 c4 47 1a b5   ..s..6..?J.r.G..
    0040 - d2 43 6c a7 97 39 8b f3-4e 7c e2 9e 23 15 9c 86   .Cl..9..N|..#...
    0050 - 5e 83 b4 bb e1 bf 7a cc-99 09 b4 9a 0b e8 be 7a   ^.....z........z
    0060 - bc e0 0c 8e 54 7c 72 98-e7 ed 1f 5b d9 58 29 c3   ....T|r....[.X).
    0070 - 9a 28 35 19 2a 84 21 71-38 21 e1 0b 0c 86 e5 45   .(5.*.!q8!.....E
    0080 - a9 c2 13 e3 e2 45 75 7d-ed 77 2d 9e 27 c7 48 2a   .....Eu}.w-.'.H*
    0090 - 09 d2 cc cf 2c 07 3d 09-8f b6 33 d7 de 03 b3 11   ....,.=...3.....
    00a0 - f6 a4 fd be a2 78 3d 3a-43 f7 ed 43 34 35 ca e7   .....x=:C..C45..
    00b0 - 58 08 36 e0 1e a9 b4 b0-49 15 61 3a 4f 20 6f 1c   X.6.....I.a:O o.
    00c0 - be 79 6e d2 a8 60 ba 40-83 66 90 29 a8 8a ba 53   .yn..`.@.f.)...S

    Start Time: 1662271539
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
    Session-ID: 0798D88B76621E4703B030E86DDFF27DEE559AAF75BD56FAB4EB6A7C967883BC
    Session-ID-ctx: 
    Resumption PSK: 0A2C9C3065843ACC64A66393F6E332A0E31F68D4E4B458A9DCE18DFAB3F45C9FE6CA88F448B028F57A98D2D17ADF1168
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 09 86 a0 aa 25 48 38 1d-0e b1 8d f8 fa 82 ac 33   ....%H8........3
    0010 - 5f f1 fd 24 10 ee 77 38-df b6 41 b5 f9 c0 73 c6   _..$..w8..A...s.
    0020 - 3e d0 4d b1 59 d3 6b 31-fe 42 21 4a 4b 10 95 62   >.M.Y.k1.B!JK..b
    0030 - 9a a0 11 74 cb 1c f2 b4-90 b1 f7 ad 03 44 05 fe   ...t.........D..
    0040 - 92 57 36 c2 76 61 5e 48-0b fb 1e ec c2 58 b2 60   .W6.va^H.....X.`
    0050 - 6f e3 d0 2f dc 82 32 2d-18 b6 c2 d4 95 59 53 25   o../..2-.....YS%
    0060 - d0 de 11 ff 0e a3 fb c5-45 10 13 17 6b b8 a3 44   ........E...k..D
    0070 - 86 c2 3b 98 cc bb 33 a4-05 c0 c4 80 8b 1d 7d a3   ..;...3.......}.
    0080 - 68 58 90 c6 8f a9 02 61-de e8 35 d7 30 56 e8 af   hX.....a..5.0V..
    0090 - f2 30 3b 72 c8 d6 d6 1b-5f b6 73 97 79 04 11 ad   .0;r...._.s.y...
    00a0 - ca 60 46 ed 68 07 fd 9a-9c 35 8a ca 43 a2 c9 35   .`F.h....5..C..5
    00b0 - 17 c0 26 d8 dc 2c b4 a4-26 c2 dc 3a 4c 95 83 18   ..&..,..&..:L...
    00c0 - e2 63 8b 2f 15 f5 f1 e3-74 ed 60 6d 2e d0 6a 61   .c./....t.`m..ja

    Start Time: 1662271539
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```