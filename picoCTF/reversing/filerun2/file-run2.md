# File Run 2

## DEscripcion
Another program, but this time, it seems to want some input. What happens if you try to run it on the command line with input "Hello!"? Download the program [here](https://artifacts.picoctf.net/c/352/run).

## Accesos
Try running it and add the phrase "Hello!" with a space in front (i.e. "./run Hello!")

## Solucion
```console              
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ chmod +x ./run                              
                                                                                                                           
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ ./run         
Run this file with only one argument.
                                                                                                                           
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$ ./run Hello!
The flag is: picoCTF{F1r57_4rgum3n7_96f2195f}  

```


## Referencias