# Local Authority

## DEscripcion
Can you get the flag? Go to this [website](http://saturn.picoctf.net:49699/) and see what you can discover.

## Accesos
How is the password checked on this website?

## Solucion
```html
    <title>Login Page</title>
  </head>
  <body>
    <script src="[secure.js](view-source:http://saturn.picoctf.net:49699/secure.js)"></script>
```
```js
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```


picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb} 