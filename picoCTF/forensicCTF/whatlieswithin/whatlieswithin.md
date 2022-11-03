## What Lies With In

# Descripcion
There's something in the building. Can you retrieve the flag?

# Datos de acceso
png

# Solucion
```console

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/whatlieswithin]
└─$ file buildings.png
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/whatlieswithin]
└─$ xxd buildings.png | head
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 0291 0000 01b6 0806 0000 0027 6add  .............'j.
00000020: d800 0020 0049 4441 5478 5eac bd4d 8b24  ... .IDATx^..M.$
00000030: 6b96 2676 d2ca dada daca da70 b95c 2ec7  k.&v.......p.\..
00000040: e504 4128 95a4 2e97 a210 4d33 2b21 b41a  ..A(......M3+!..
00000050: f403 b4d6 cf98 8516 6216 4208 2d06 a185  ........b.B.-...
00000060: 16c3 d088 6218 865e 348d 6886 6610 4333  ....b..^4.h.f.C3
00000070: 1445 5134 cde5 9224 4910 0431 8ecb 71f9  .EQ4...$I..1..q.
00000080: f8f8 d858 59db b5b2 b214 cf73 ce6b ef6b  ...XY......s.k.k
00000090: e6ee 91f7 7677 d447 64b8 dbc7 fb79 cef3  ....vw.Gd....y..

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/whatlieswithin]
└─$ open buildings.png

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/whatlieswithin]
└─$ zsteg
zsteg: command not found

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/whatlieswithin]
└─$ sudo gem install zsteg
[sudo] contraseña para yareds45:
Fetching zpng-0.4.3.gem
Fetching rainbow-3.1.1.gem
Fetching zsteg-0.2.11.gem
Fetching iostruct-0.0.4.gem
Successfully installed rainbow-3.1.1
Successfully installed zpng-0.4.3
Successfully installed iostruct-0.0.4
Successfully installed zsteg-0.2.11
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for zpng-0.4.3
Installing ri documentation for zpng-0.4.3
Parsing documentation for iostruct-0.0.4
Installing ri documentation for iostruct-0.0.4
Parsing documentation for zsteg-0.2.11
Installing ri documentation for zsteg-0.2.11
Done installing documentation for rainbow, zpng, iostruct, zsteg after 1 seconds
4 gems installed

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/whatlieswithin]
└─$ zsteg
Usage: zsteg [options] filename.png [param_string]

    -c, --channels X                 channels (R/G/B/A) or any combination, comma separated
                                     valid values: r,g,b,a,rg,bgr,rgba,r3g2b3,...
    -l, --limit N                    limit bytes checked, 0 = no limit (default: 256)
    -b, --bits N                     number of bits, single int value or '1,3,5' or range '1-8'
                                     advanced: specify individual bits like '00001110' or '0x88'
        --lsb                        least significant BIT comes first
        --msb                        most significant BIT comes first
    -P, --prime                      analyze/extract only prime bytes/pixels
        --invert                     invert bits (XOR 0xff)
    -a, --all                        try all known methods
    -o, --order X                    pixel iteration order (default: 'auto')
                                     valid values: ALL,xy,yx,XY,YX,xY,Xy,bY,...
    -E, --extract NAME               extract specified payload, NAME is like '1b,rgb,lsb'

        --[no-]file                  use 'file' command to detect data type (default: YES)
        --no-strings                 disable ASCII strings finding (default: enabled)
    -s, --strings X                  ASCII strings find mode: first, all, longest, none
                                     (default: first)
    -n, --min-str-len X              minimum string length (default: 8)
        --shift N                    prepend N zero bits

    -v, --verbose                    Run verbosely (can be used multiple times)
    -q, --quiet                      Silent any warnings (can be used multiple times)
    -C, --[no-]color                 Force (or disable) color output (default: auto)

PARAMS SHORTCUT
        zsteg fname.png 2b,b,lsb,xy  ==>  --bits 2 --channel b --lsb --order xy

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/whatlieswithin]
└─$ zsteg -a buildings.png | grep picoCTF
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
```
