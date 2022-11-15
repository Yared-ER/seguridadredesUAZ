#  tunn3l v1s10n

#### Description
We found this [file](https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n). Recover the flag.

## Accesos

Weird that it won't display right...

## Solucion
Corroboramos  el formato bmp
corroboramos el tamanio y la hacemo un poco mas grande hacia arriba para ver la  bandera.
```bash
  ┌──(yareds45㉿yareds45)-[~/develop]
└─$ ls                                       
tunn3l_v1s10n
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ file  tunn3l_v1s10n                      
tunn3l_v1s10n: data
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ xxd tunn3l_v1s10n | head 
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ mv  tunn3l_v1s10n tunn3l_v1s10n.bmp 
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ open  tunn3l_v1s10n.bmp 
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ Gtk-Message: 16:32:38.981: Failed to load module "gail"

** (gimp-2.10:13538): WARNING **: 16:32:38.989: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ hexeditor tunn3l_v1s10n.bmp 
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ open  tunn3l_v1s10n.bmp    
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ Gtk-Message: 16:35:59.501: Failed to load module "gail"

** (gimp-2.10:14548): WARNING **: 16:35:59.507: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ open  tunn3l_v1s10n     
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ hexeditor tunn3l_v1s10n.bmp

                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ open  tunn3l_v1s10n

picoCTF{qu1t3_a_v13w_2020}


```


## Referencias
