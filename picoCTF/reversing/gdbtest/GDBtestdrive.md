# GDB Test Drive

## Descripcion
Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/116/gdbme). Here's the test drive instructions:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`

## Solucion


```console
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ chmod +x gdbme                                
                                                                                                                           
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ ls
gdbme
                                                                                                                                                                                                                                        
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ gdb gdbme
GNU gdb (Debian 12.1-3) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm
Undefined command: "layout".  Try "help".
(gdb) layout asm
Undefined command: "layout".  Try "help".
(gdb) break *(main+99)
Breakpoint 1 at 0x132a
(gdb) run
Starting program: /home/masterfer/Downloads/PicoCTF/Reversing22/gdbtestdrive/gdbme 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055555555532a in main ()
(gdb) jump  *(main+104)
Continuing at 0x55555555532f.
picoCTF{d3bugg3r_dr1v3_72bd8355}
[Inferior 1 (process 8514) exited normally]


```
picoCTF{d3bugg3r_dr1v3_72bd8355}
## Referencias
https://www.youtube.com/watch?v=Tmdnsre9z7s
