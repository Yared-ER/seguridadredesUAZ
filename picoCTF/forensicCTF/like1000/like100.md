# like1000

#### Description
This [.tar file](https://jupiter.challenges.picoctf.org/static/52084b5ad360b25f9af83933114324e0/1000.tar) got tarred a lot.

## Hints
Try and script this, it'll save you a lot of time

## Solucion

```bash
──(yareds45㉿yareds45)-[~/develop]
└─$ wget https://jupiter.challenges.picoctf.org/static/52084b5ad360b25f9af83933114324e0/1000.tar
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ tar  -tf 1000.tar
┌──(yareds45㉿yareds45)-[~/develop]
└─$ tar  -xvf 999.tar 

                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ for  i in {1000..1}; do tar -xvf $i.tar; done
┌──(yareds45㉿yareds45)-[~/develop]
└─$ open flag.png 

```

picoCTF{l0t5_0f_TAR5}


## Referencias