## GET YOUR FLAG

# Descripcion

Through tools look for the flag in this binary

# Recursos

- Archivo binario

# Solution

```shell

──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$ file b1n@ri0
b1n@ri0: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=506b7be935d8940c672ab0d40d2e03ebd746155b, with debug_info, not stripped

┌──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$ cat b1n@ri0 | head
ELF>@8"@8       @"!@@888

 XX/lib64/ld-linux-x86-64.so.2GNUGNUPk{5ؔ
.F[K                                    g*
     -&g v "libc.so.6putsprintf__cxa_finalizestrcmp__libc_start_mainGLIBC_2.2.5_ITM_deregisterTMCloneTable__gmon_sta        H}egisterTMCloneTableui   ?
 Ht5*
 %,
 @%*
 h%"
 h%
 h%2
cH=I^HHP DH=

┌──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$ cat b1n@ri0 | grep flag
grep: (entrada estándar): coincidencia en fichero binario

┌──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$ cat b1n@ri0 | grep CTF

┌──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$ cat b1n@ri0 | grep CTF

┌──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$ cat b1n@ri0 | grep flag
grep: (entrada estándar): coincidencia en fichero binario

┌──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$ strings b1n@ri0 | flag
Command 'flag' not found, did you mean:
  command 'flog' from deb flog
  command 'flac' from deb flac
  command 'blag' from deb blag
  command 'mflag' from deb mblaze
Try: sudo apt install <deb name>

┌──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$ strings b1n@ri0 | grep flag
Oh, help? I actually don't do much, but I do have this flag here: flag{T3@m_H3rE_1s_yU0r_Fl@G_XD}"@@@@@
_flags
/opt/hacksports/shared/staging/Wave a flag_2_9470317830239579/problem_files
_flags2

┌──(yareds45㉿yareds45)-[~/…/metaCTF/peru/foresinc/getyourflag]
└─$

```

