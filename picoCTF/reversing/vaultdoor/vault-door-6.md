# vault-door-6

## Descripcion
This vault uses an XOR encryption scheme. The source code for this vault is here: [VaultDoor6.java](https://jupiter.challenges.picoctf.org/static/cdb33ffba609e2521797aac66320ec65/VaultDoor6.java)
## Accesos
If X ^ Y = Z, then Z ^ Y = X. Write a program that decrypts the flag based on this fact.


## Solucion
```python
>>> mybytes = [0x3b, 0x65, 0x21, 0xa , 0x38, 0x0 , 0x36, 0x1d,
...             0xa , 0x3d, 0x61, 0x27, 0x11, 0x66, 0x27, 0xa ,
...             0x21, 0x1d, 0x61, 0x3b, 0xa , 0x2d, 0x65, 0x27,
...             0xa , 0x6c, 0x60, 0x37, 0x30, 0x60, 0x31, 0x36]
>>> flag = [i ^ 0x55 for i in mybytes]
>>> flag = [ chr(i) for i in flag ]
>>> ''.join(flag)
'n0t_mUcH_h4rD3r_tH4n_x0r_95be5dc'




picoCTF{n0t_mUcH_h4rD3r_tH4n_x0r_95be5dc}
```


## Referencias