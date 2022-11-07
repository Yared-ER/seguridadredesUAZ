## Find A Flag

# Descripcion
Unzip this archive and find the file named 'oliver\_twist.txt'

# Solucion
```console
┌──(masterfer㉿PcMaster)-[~/Downloads/PicoCTF/concuross/findflag176]
└─$ unzip great_author.zip 
Archive:  great_author.zip
   creating: great_author/
  inflating: great_author/14789.txt.utf-8  
  inflating: great_author/13771.txt.utf-8  
   creating: great_author/adequate_books/
  inflating: great_author/adequate_books/44578.txt.utf-8  
  inflating: great_author/adequate_books/46804-0.txt  
   creating: great_author/adequate_books/more_books/
   creating: great_author/adequate_books/more_books/.secret/
   creating: great_author/adequate_books/more_books/.secret/deeper_secrets/
   creating: great_author/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
 extracting: great_author/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/Oliver_Twist.txt  
  inflating: great_author/adequate_books/more_books/1023.txt.utf-8  
   creating: great_author/satisfactory_books/
  inflating: great_author/satisfactory_books/16021.txt.utf-8  
   creating: great_author/satisfactory_books/more_books/
  inflating: great_author/satisfactory_books/more_books/37121.txt.utf-8  
  inflating: great_author/satisfactory_books/23765.txt.utf-8  
   creating: great_author/acceptable_books/
  inflating: great_author/acceptable_books/17879.txt.utf-8  
  inflating: great_author/acceptable_books/17880.txt.utf-8  
   creating: great_author/acceptable_books/more_books/
  inflating: great_author/acceptable_books/more_books/40723.txt.utf-8 



┌──(masterfer㉿PcMaster)-[~/…/PicoCTF/concuross/findflag176/great_author]
└─$ find /home/masterfer/Downloads/PicoCTF/concuross/findflag176/great_author -name "*.txt" 
/home/masterfer/Downloads/PicoCTF/concuross/findflag176/great_author/adequate_books/46804-0.txt
/home/masterfer/Downloads/PicoCTF/concuross/findflag176/great_author/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/Oliver_Twist.txt
                                                                                                      
┌──(masterfer㉿PcMaster)-[~/…/PicoCTF/concuross/findflag176/great_author]
└─$ cd adequate_books/more_books/.secret 
                                                                                                      
┌──(masterfer㉿PcMaster)-[~/…/great_author/adequate_books/more_books/.secret]
└─$ ls  -la
total 12
drwxrwxr-x 3 masterfer masterfer 4096 May 13 15:14 .
drwxrwxr-x 3 masterfer masterfer 4096 Oct  5 22:02 ..
drwxrwxr-x 3 masterfer masterfer 4096 May 13 15:15 deeper_secrets
                                                                                                      
┌──(masterfer㉿PcMaster)-[~/…/great_author/adequate_books/more_books/.secret]
└─$ cd deeper_secrets                   
                                                                                                      
┌──(masterfer㉿PcMaster)-[~/…/adequate_books/more_books/.secret/deeper_secrets]
└─$ ls -la 
total 12
drwxrwxr-x 3 masterfer masterfer 4096 May 13 15:15 .
drwxrwxr-x 3 masterfer masterfer 4096 May 13 15:14 ..
drwxrwxr-x 2 masterfer masterfer 4096 Oct  5 22:08 deepest_secrets
                                                                                                      
┌──(masterfer㉿PcMaster)-[~/…/adequate_books/more_books/.secret/deeper_secrets]
└─$ cd  deepest_secrets 
                                                                                                      
┌──(masterfer㉿PcMaster)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ ls  -la
total 12
drwxrwxr-x 2 masterfer masterfer 4096 Oct  5 22:08 .
drwxrwxr-x 3 masterfer masterfer 4096 May 13 15:15 ..
-rw-r--r-- 1 masterfer masterfer   23 Oct  5 22:06 Oliver_Twist.txt
                                                                                                      
┌──(masterfer㉿PcMaster)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ cat Oliver_Twist.txt 
fl@g{Ch@rRl3$_D1cK3N$}


```
