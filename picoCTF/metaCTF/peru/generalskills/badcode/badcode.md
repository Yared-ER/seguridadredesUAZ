## Bad Code

# Descripcion
Help us review this code in this file

# Solucion
```console
┌──(masterfer㉿PcMaster)-[~/Downloads/PicoCTF/concuross/badcode]
└─$ python3 badcode.py 
  File "/home/masterfer/Downloads/PicoCTF/concuross/badcode/badcode.py", line 13
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
                                                                                                         ^
IndentationError: unindent does not match any outer indentation level


┌──(masterfer㉿PcMaster)-[~/Downloads/PicoCTF/concuross/badcode]
└─$ python3 badcode.py
  File "/home/masterfer/Downloads/PicoCTF/concuross/badcode/badcode.py", line 16
    flag_enc = chr(0x01) + chr(0x21) + chr(0x08) + chr(0x19) + chr(0x21) + chr(0x51) + chr(0x5c) + chr(0x4>
             ^
SyntaxError: invalid syntax




┌──(masterfer㉿PcMaster)-[~/Downloads/PicoCTF/concuross/badcode]
└─$ python3 badcode.py
  File "/home/masterfer/Downloads/PicoCTF/concuross/badcode/badcode.py", line 13
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)>
                   ^
SyntaxError: '[' was never closed



┌──(masterfer㉿PcMaster)-[~/Downloads/PicoCTF/concuross/badcode]
└─$ python3 badcode.py
  File "/home/masterfer/Downloads/PicoCTF/concuross/badcode/badcode.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent


┌──(masterfer㉿PcMaster)-[~/Downloads/PicoCTF/concuross/badcode]
└─$ python3 badcode.py
That is correct! Here's your flag: dOcpE$9


┌──(masterfer㉿PcMaster)-[~/Downloads/PicoCTF/concuross/badcode]
└─$ python3 badcode.py
That is correct! Here's your flag: dOcpE$9.QM9TEiam
```
