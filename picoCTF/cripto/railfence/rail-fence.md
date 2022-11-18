# rail-fence

## Description
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it? Download the message [here](https://artifacts.picoctf.net/c/273/message.txt). Put the decoded message in the picoCTF flag format, `picoCTF{decoded_message}`.

## Accesos
Once you've understood how the cipher works, it's best to draw it out yourself on paper

## Solucion

```bash
┌──(yareds45㉿yareds45)-[~/develop]
└─$ ls
message.txt  Rail_fence_cipher
                                                                                                
┌──(yareds45㉿yareds45)-[~/develop]
└─$ cat message.txt      
Ta _7N6D8Dhlg:W3D_H3C31N__387ef sHR053F38N43DFD i33___N6 

cyberchef y buscamos rail fence decode y pegamos el mensaje.txt
con la llave 4 y el offset 0

lo cual nos da:
The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_83F6D8D7

picoCTF{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_83F6D8D7}
```


## Referencias
https://gchq.github.io/CyberChef/