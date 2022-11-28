# asm2

## Descripcion
What does asm2(0x4,0x21) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/7e3eb2f90200ac88126f62ceb4bc3948/test.S)

## Accesos
assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)

## Solucion

```bash
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ cat test.S 
asm2:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  add    DWORD PTR [ebp-0x8],0x74
        <+28>:  cmp    DWORD PTR [ebp-0x8],0xfb46
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]
        <+40>:  leave  
        <+41>:  ret  



  GNU nano 6.3                                    test1.py *                                           
[0x78   ]ebp - 0x8
[0x22   ]ebp - 0x4
[ebp    ] < ebp   
[ret    ] < ebp + 0x4
[0x4    ] ebp + 0x8
[0x21   ]ebp + 0xc 

 
registers
[0x24c  ]eax
```


```console
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ python3
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x4 <= 0xfb46
True
>>> hex(0x4 + 0x74)
'0x78'
>>> 0x78 <=0xfb46
True
>>> 0xfb46 / 0x74
554.5344827586207
>>> int(ox21)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'ox21' is not defined
>>> int(0x21)
33
>>> hex(555+33)
'0x24c'


```


## Referencias