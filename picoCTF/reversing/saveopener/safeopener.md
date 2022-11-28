# Safe Opener

## Descripcion
Can you open this safe? I forgot the key to my safe but this [program](https://artifacts.picoctf.net/c/463/SafeOpener.java) is supposed to help me with retrieving the lost key. Can you help me unlock my safe? Put the password you recover into the picoCTF flag format like: `picoCTF{password}`
## Solucion


```java

Base64.Encoder encoder = Base64.getEncoder();



    public static boolean openSafe(String password) {
        String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";
        
        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        else {
            System.out.println("Password is incorrect\n");
            return false;
        }
    }
}             


```
```console
┌──(yareds45㉿yareds45)-[~/develop/reversing]
└─$echo 'cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz' | base64 -d
pl3as3_l3t_m3_1nt0_th3_saf3 
picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}
```

## Referencias
https://www.youtube.com/watch?v=zhtc12sZ61U