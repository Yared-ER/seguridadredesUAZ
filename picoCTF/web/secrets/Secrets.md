# Secrets

## Descripcion
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:50167/).

## accesos
folders folders folders

## Solucion 
- [pasos de html]
```html
 <title>home</title>
    <!-- css -->
    <link href="[secret/assets/index.css](view-source:http://saturn.picoctf.net:50167/secret/assets/index.css)" rel="stylesheet" />
  </head>
  <body>
```
- [1.- inspeccionamos el codigo y vemos assets con el secret ]
view-source:http://saturn.picoctf.net:50167/secret/

aqui vemos un css hidden asi que vamos a la ruta
```html
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="[hidden/file.css](view-source:http://saturn.picoctf.net:50167/secret/hidden/file.css)" />
  </head>
```

view-source:http://saturn.picoctf.net:50167/secret/hidden/

```html
<html>
  <head>
    <title>LOGIN</title>
    <!-- css -->
    <link href="[superhidden/login.css](view-source:http://saturn.picoctf.net:50167/secret/hidden/superhidden/login.css)" rel="stylesheet" />
  </head>
  <body>
```

view-source:http://saturn.picoctf.net:50167/secret/hidden/superhidden/
```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="[mycss.css](view-source:http://saturn.picoctf.net:50167/secret/hidden/superhidden/mycss.css)" />
  </head>

  <body>
    <h1>Finally. You found me. But can you see me</h1>
    <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_51b260fe}</h3>
  </body>
</html>
```

picoCTF{succ3ss_@h3n1c@10n_51b260fe}