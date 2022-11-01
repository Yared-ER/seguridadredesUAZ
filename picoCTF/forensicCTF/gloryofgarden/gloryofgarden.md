## Glory of garden

# Descripcion

This garden contains more than it seems.

# Datos de acceso
garden.jpg

# Solucion

'''shell
┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/gloryofgarden]
└─$ open garden.jpg

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/gloryofgarden]
└─$ file garden.jpg
garden.jpg: JPEG image data, 
JFIF standard 1.01, resolution (DPI), 
density 72x72, segment length 16, baseline, precision 8, 
2999x2249, components 3

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/gloryofgarden]
└─$ hexeditor garden.jpg

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/gloryofgarden]
└─$ strings garden.jpg | grep picoCTF
Here is a flag "picoCTF{more_than_m33ts_the_3y33dd2eEF5}"

┌──(yareds45㉿yareds45)-[~/…/seguridadredesUAZ/picoCTF/forensicCTF/gloryofgarden]
└─$

'''

