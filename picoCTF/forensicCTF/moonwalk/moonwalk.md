## MoonWalk

# Descripcion
Decode this message from the moon.

# Solucion
```console

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/moonwalk]
└─$ file message.wav
message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/moonwalk]
└─$ strings message.wav | grep picoCTF

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/moonwalk]
└─$ strings message.wav | head
RIFFn
WAVEfmt
dataH
        N       ^
b       q
O       ,       1
J       I
D       6
!""D!
        G       A

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/moonwalk]
└─$ sstv -d message.wav -o message.png
[sstv] Searching for calibration header... Found!
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [####################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/moonwalk]
└─$ ls
message.png  message.wav  moonwalk.md

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/moonwalk]
└─$ open message.png

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/moonwalk]
└─$
```

## Image
![Image text](https://github.com/Yared-ER/seguridadredesUAZ/blob/main/capturas-pantallas/moonwalk/moonwalkcap.png )
