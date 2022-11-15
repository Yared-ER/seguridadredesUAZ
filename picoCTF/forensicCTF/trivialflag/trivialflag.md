# Trivial Flag Transfer Protocol

#### Description
Figure out how they moved the [flag](https://mercury.picoctf.net/static/fb24ddcfaf1e297be525ba7474964fa5/tftp.pcapng).

## Acceso directos
What are some other ways to hide data?

## Solucion

```bash
┌──(yareds45㉿yareds45)-[~/develop]
└─$ wget https://mercury.picoctf.net/static/fb24ddcfaf1e297be525ba7474964fa5/tftp.pcapng
--2022-10-23 17:15:37--  https://mercury.picoctf.net/static/fb24ddcfaf1e297be525ba7474964fa5/tftp.pcapng
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 52116496 (50M) [application/octet-stream]
Saving to: ‘tftp.pcapng’

tftp.pcapng             100%[===============================>]  49.70M   981KB/s    in 36s     

2022-10-23 17:16:13 (1.40 MB/s) - ‘tftp.pcapng’ saved [52116496/52116496]

                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ ls
'instructions(1).txt'   picture1.bmp      'picture3(1).bmp'  'plan(1)'          tftp.pcapng
 instructions.txt      'picture2(1).bmp'   picture3.bmp      'program(1).deb'
'picture1(1).bmp'       picture2.bmp       plan               program.deb
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat instructions.txt | tr [A-Z] [N-ZA-M]  
TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat plan | tr [A-Z] [N-ZA-M]
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ sudo dpkg -i program.deb   
dpkg: warning: downgrading steghide from 0.5.1-15 to 0.5.1-9.1+b1
(Reading database ... 607173 files and directories currently installed.)
Preparing to unpack program.deb ...
Unpacking steghide (0.5.1-9.1+b1) over (0.5.1-15) ...
Setting up steghide (0.5.1-9.1+b1) ...
Processing triggers for man-db (2.10.2-1) ...
Processing triggers for kali-menu (2022.3.1) ...
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ steghide --extract -sf picture1.bmp
Enter passphrase: 
steghide: could not extract any data with that passphrase!
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ steghide --extract -sf picture1.bmp -p DUEDILIGENCE
steghide: could not extract any data with that passphrase!
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ steghide --extract -sf picture2.bmp -p DUEDILIGENCE
steghide: could not extract any data with that passphrase!
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ steghide --extract -sf picture3.bmp -p DUEDILIGENCE
wrote extracted data to "flag.txt".
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat flag.txt                
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}

```

picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
## Referencias