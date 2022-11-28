# asm3

## Descripcion
What does asm3(0xd2c26416,0xe6cf51f0,0xe54409d5) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/df999527eaecf46f259c4337a820856c/test.S)

## Accesos
assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)

## Solucion

```bash
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ cat test2.S 
start:
	push 0xe54409d5
	push 0xe6cf51f0
	push 0xd2c26416
	call asm3
asm3:
        push   ebp
        mov    ebp,esp
        xor    eax,eax
        mov    ah,BYTE PTR [ebp+0x9]
        shl    ax,0x10
        sub    al,BYTE PTR [ebp+0xe]
        add    ah,BYTE PTR [ebp+0xf]
        xor    ax,WORD PTR [ebp+0x12]
        nop
        pop    ebp
        ret  



WINDOWS Y REGISTERS

[0x00000375]eax

0x375

```


## Referencias

https://carlosrafaelgn.com.br/Asm86/