10.129.127.62



└─$ nmap -sC -sV 10.129.127.62 -oA module-2-knowledge-check
Starting Nmap 7.95 ( https://nmap.org ) at 2025-11-22 20:06 CST
Nmap scan report for 10.129.127.62
Host is up (0.067s latency).
Not shown: 998 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 4c:73:a0:25:f5:fe:81:7b:82:2b:36:49:a5:4d:c8:5e (RSA)
|   256 e1:c0:56:d0:52:04:2f:3c:ac:9a:e7:b1:79:2b:bb:13 (ECDSA)
|_  256 52:31:47:14:0d:c3:8e:15:73:e3:c4:24:a2:3a:12:77 (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
| http-robots.txt: 1 disallowed entry 
|_/admin/
|_http-server-header: Apache/2.4.41 (Ubuntu)
|_http-title: Welcome to GetSimple! - gettingstarted
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


what web

ERROR Opening: https://10.129.127.62 - Connection refused - connect(2) for "10.129.127.62" port 443
http://10.129.127.62 [200 OK] AddThis, Apache[2.4.41], Country[RESERVED][ZZ], HTML5, HTTPServer[Ubuntu Linux][Apache/2.4.41 (Ubuntu)], IP[10.129.127.62], Script[text/javascript], Title[Welcome to GetSimple! - gettingstarted]
                                                                             
┌──(kali㉿kali)-[~/projects/module-2/knowledge-check]
└─$ 



┌──(kali㉿kali)-[~/projects/module-2/knowledge-check]
└─$ gobuster dir -u http://10.129.127.62 --wordlist /usr/share/wordlists/dirb/common.txt 
===============================================================
Gobuster v3.8
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.129.127.62
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirb/common.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.8
[+] Timeout:                 10s
===============================================================
Starting gobuster in directory enumeration mode
===============================================================
/.hta                 (Status: 403) [Size: 278]
/.htpasswd            (Status: 403) [Size: 278]
/.htaccess            (Status: 403) [Size: 278]
/admin                (Status: 301) [Size: 314] [--> http://10.129.127.62/admin/]                                                                         
/backups              (Status: 301) [Size: 316] [--> http://10.129.127.62/backups/]                                                                       
/data                 (Status: 301) [Size: 313] [--> http://10.129.127.62/data/]                                                                          
/index.php            (Status: 200) [Size: 5485]
/plugins              (Status: 301) [Size: 316] [--> http://10.129.127.62/plugins/]                                                                       
/robots.txt           (Status: 200) [Size: 32]
/server-status        (Status: 403) [Size: 278]
/sitemap.xml          (Status: 200) [Size: 431]
/theme                (Status: 301) [Size: 314] [--> http://10.129.127.62/theme/]                                                                         
Progress: 4613 / 4613 (100.00%)
===============================================================
Finished
===============================================================
                                  




GetSimpleCMS

```
┌──(kali㉿kali)-[~/projects/module-2/knowledge-check]
└─$ curl 10.129.127.62
<!DOCTYPE html>
<!--[if lt IE 7 ]> <html lang="en" class="ie6"> <![endif]-->
<!--[if IE 7 ]>    <html lang="en" class="ie7"> <![endif]-->
<!--[if IE 8 ]>    <html lang="en" class="ie8"> <![endif]-->
<!--[if IE 9 ]>    <html lang="en" class="ie9"> <![endif]-->
<!--[if (gt IE 9)|!(IE)]><!--> <html lang="en" > <!--<![endif]-->
<head>
<meta charset="utf-8">

  <title>Welcome to GetSimple! - gettingstarted</title>

        <meta name="robots" content="index, follow">

        <link href='//fonts.googleapis.com/css?family=Yanone+Kaffeesatz' rel='stylesheet' type='text/css'>
        <link href="http://gettingstarted.htb/theme/Inno
....
                        <div class="left">2025 <a href="http://gettingstarted.htb/" >gettingstarted</a></div>
                        <div class="right">Innovation Theme by <a href="http://www.cagintranet.com" >Cagintranet</a> &middot; <a href="http://get-simple.info/" target="_blank" >Powered by  GetSimple</a></div>
                </div>
        </footer>
         
</body>
</html>                                



```

──(kali㉿kali)-[~/projects/module-2/knowledge-check]
└─$ searchsploit getsimple 
------------------------------------------- ---------------------------------
 Exploit Title                             |  Path
------------------------------------------- ---------------------------------
Getsimple CMS 2.01 - 'changedata.php' Cros | php/webapps/34789.html
Getsimple CMS 2.01 - 'components.php' Cros | php/webapps/34041.txt
Getsimple CMS 2.01 - Local File Inclusion  | php/webapps/12517.txt
Getsimple CMS 2.01 - Multiple Vulnerabilit | php/webapps/14338.html
Getsimple CMS 2.01 < 2.02 - Administrative | php/webapps/15605.txt
Getsimple CMS 2.03 - 'upload-ajax.php' Arb | php/webapps/35353.txt
Getsimple CMS 3.0 - 'set' Local File Inclu | php/webapps/35726.py
Getsimple CMS 3.1.2 - 'path' Local File In | php/webapps/37587.txt
Getsimple CMS 3.2.1 - Arbitrary File Uploa | php/webapps/25405.txt
GetSimple CMS 3.3.1 - Cross-Site Scripting | php/webapps/43888.txt
Getsimple CMS 3.3.1 - Persistent Cross-Sit | php/webapps/32502.txt
Getsimple CMS 3.3.10 - Arbitrary File Uplo | php/webapps/40008.txt
GetSimple CMS 3.3.13 - Cross-Site Scriptin | php/webapps/44408.txt
GetSimple CMS 3.3.16 - Persistent Cross-Si | php/webapps/48850.txt
GetSimple CMS 3.3.16 - Persistent Cross-Si | php/webapps/49726.py
GetSimple CMS 3.3.4 - Information Disclosu | php/webapps/49928.py
GetSimple CMS Custom JS 0.1 - Cross-Site R | php/webapps/49816.py
Getsimple CMS Items Manager Plugin - 'PHP. | php/webapps/37472.php
GetSimple CMS My SMTP Contact Plugin 1.1.1 | php/webapps/49774.py
GetSimple CMS My SMTP Contact Plugin 1.1.2 | php/webapps/49798.py
GetSimple CMS Plugin Multi User 1.8.2 - Cr | php/webapps/48745.txt
GetSimple CMS v3.3.16 - Remote Code Execut | php/webapps/51475.py
GetSimpleCMS - Unauthenticated Remote Code | php/remote/46880.rb
GetSimpleCMS 3.3.16 - Remote Code Executio | php/webapps/52168.txt
------------------------------------------- --------------------------------



└─$ searchsploit apache 2.4.41
------------------------------------------- ---------------------------------
 Exploit Title                             |  Path
------------------------------------------- ---------------------------------
Apache + PHP < 5.3.12 / < 5.4.2 - cgi-bin  | php/remote/29290.c
Apache + PHP < 5.3.12 / < 5.4.2 - Remote C | php/remote/29316.py
Apache CXF < 2.5.10/2.6.7/2.7.4 - Denial o | multiple/dos/26710.txt
Apache mod_ssl < 2.8.7 OpenSSL - 'OpenFuck | unix/remote/21671.c
Apache mod_ssl < 2.8.7 OpenSSL - 'OpenFuck | unix/remote/47080.c
Apache mod_ssl < 2.8.7 OpenSSL - 'OpenFuck | unix/remote/764.c
Apache OpenMeetings 1.9.x < 3.1.0 - '.ZIP' | linux/webapps/39642.txt
Apache Tomcat < 5.5.17 - Remote Directory  | multiple/remote/2061.txt
Apache Tomcat < 6.0.18 - 'utf8' Directory  | multiple/remote/6229.txt
Apache Tomcat < 6.0.18 - 'utf8' Directory  | unix/remote/14489.c
Apache Tomcat < 9.0.1 (Beta) / < 8.5.23 /  | jsp/webapps/42966.py
Apache Tomcat < 9.0.1 (Beta) / < 8.5.23 /  | windows/webapps/42953.txt
Apache Xerces-C XML Parser < 3.1.2 - Denia | linux/dos/36906.txt
Webfroot Shoutbox < 2.32 (Apache) - Local  | linux/remote/34.pl
------------------------------------------- ---------------------------



┌──(kali㉿kali)-[~/projects/module-2/knowledge-check]
└─$ searchsploit "OpenSSH"      
------------------------------------------- ---------------------------------
 Exploit Title                             |  Path
------------------------------------------- ---------------------------------
Debian OpenSSH - (Authenticated) Remote SE | linux/remote/6094.txt
Dropbear / OpenSSH Server - 'MAX_UNAUTH_CL | multiple/dos/1572.pl
FreeBSD OpenSSH 3.5p1 - Remote Command Exe | freebsd/remote/17462.txt
glibc-2.2 / openssh-2.3.0p1 / glibc 2.1.9x | linux/local/258.sh
Novell Netware 6.5 - OpenSSH Remote Stack  | novell/dos/14866.txt
OpenSSH 1.2 - '.scp' File Create/Overwrite | linux/remote/20253.sh
OpenSSH 2.3 < 7.7 - Username Enumeration   | linux/remote/45233.py
OpenSSH 2.3 < 7.7 - Username Enumeration ( | linux/remote/45210.py
OpenSSH 2.x/3.0.1/3.0.2 - Channel Code Off | unix/remote/21314.txt
OpenSSH 2.x/3.x - Kerberos 4 TGT/AFS Token | linux/remote/21402.txt
OpenSSH 3.x - Challenge-Response Buffer Ov | unix/remote/21578.txt
OpenSSH 3.x - Challenge-Response Buffer Ov | unix/remote/21579.txt
OpenSSH 4.3 p1 - Duplicated Block Remote D | multiple/dos/2444.sh
OpenSSH 6.8 < 6.9 - 'PTY' Local Privilege  | linux/local/41173.c
OpenSSH 7.2 - Denial of Service            | linux/dos/40888.py
OpenSSH 7.2p1 - (Authenticated) xauth Comm | multiple/remote/39569.py
OpenSSH 7.2p2 - Username Enumeration       | linux/remote/40136.py
OpenSSH < 6.6 SFTP (x64) - Command Executi | linux_x86-64/remote/45000.c
OpenSSH < 6.6 SFTP - Command Execution     | linux/remote/45001.py
OpenSSH < 7.4 - 'UsePrivilegeSeparation Di | linux/local/40962.txt
OpenSSH < 7.4 - agent Protocol Arbitrary L | linux/remote/40963.txt
OpenSSH < 7.7 - User Enumeration (2)       | linux/remote/45939.py
OpenSSH SCP Client - Write Arbitrary Files | multiple/remote/46516.py
OpenSSH server (sshd) 9.8p1 - Race Conditi | linux/remote/52269.c
OpenSSH/PAM 3.6.1p1 - 'gossh.sh' Remote Us | linux/remote/26.sh
OpenSSH/PAM 3.6.1p1 - Remote Users Discove | linux/remote/25.c
OpenSSHd 7.2p2 - Username Enumeration      | linux/remote/40113.txt
Portable OpenSSH 3.6.1p-PAM/4.1-SuSE - Tim | multiple/remote/3303.sh
------------------------------------------- -------------------------------


Possible version 3.3.15
![[Pasted image 20251122202255.png]]

possbile api key 
<item>
<apikey>4f399dc72ff8e619e327800f851e9986</apikey>
</item>

![[Pasted image 20251122202417.png]]


plugins

# Index of /plugins
http://10.129.127.62/plugins/

|![[ICO]](http://10.129.127.62/icons/blank.gif)|[Name](http://10.129.127.62/plugins/?C=N;O=D)|[Last modified](http://10.129.127.62/plugins/?C=M;O=A)|[Size](http://10.129.127.62/plugins/?C=S;O=A)|[Description](http://10.129.127.62/plugins/?C=D;O=A)|
|---|---|---|---|---|
|---|   |   |   |   |
|![[PARENTDIR]](http://10.129.127.62/icons/back.gif)|[Parent Directory](http://10.129.127.62/)||-||
|![[   ]](http://10.129.127.62/icons/unknown.gif)|[InnovationPlugin.php](http://10.129.127.62/plugins/InnovationPlugin.php)|2018-09-07 17:58|3.3K||
|![[DIR]](http://10.129.127.62/icons/folder.gif)|[InnovationPlugin/](http://10.129.127.62/plugins/InnovationPlugin/)|2024-03-12 13:05|-||
|![[   ]](http://10.129.127.62/icons/unknown.gif)|[anonymous_data.php](http://10.129.127.62/plugins/anonymous_data.php)|2018-09-07 17:58|9.8K||
|![[DIR]](http://10.129.127.62/icons/folder.gif)|[anonymous_data/](http://10.129.127.62/plugins/anonymous_data/)|2024-03-12 13:05|-||
|---|   |   |   |   |

Apache/2.4.41 (Ubuntu) Server at 10.129.127.62 Port 80

password was admin/admin

https://www.exploit-db.com/exploits/51475




zsh gotcha

Type the following command and then press `Enter` twice:

bash

```
stty raw -echo; fg
```

This works because `stty` changes the settings and `fg` immediately brings the background process to the foreground, all before Zsh has a chance to intervene.



get user flag




www-data@gettingstarted:/var/www/html$ whoami
www-data
www-data@gettingstarted:/var/www/html$ ifconfig
ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.129.127.62  netmask 255.255.0.0  broadcast 10.129.255.255
        inet6 dead:beef::250:56ff:feb0:105f  prefixlen 64  scopeid 0x0<global>
        inet6 fe80::250:56ff:feb0:105f  prefixlen 64  scopeid 0x20<link>
        ether 00:50:56:b0:10:5f  txqueuelen 1000  (Ethernet)
        RX packets 121387  bytes 7895856 (7.8 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 116171  bytes 9469104 (9.4 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 3813  bytes 301881 (301.8 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 3813  bytes 301881 (301.8 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0



www-data@gettingstarted:/home/mrb3n$ sudo -l
Matching Defaults entries for www-data on gettingstarted:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User www-data may run the following commands on gettingstarted:
    (ALL : ALL) NOPASSWD: /usr/bin/php



copy over LinEnum using a python server

ran it but I'll focus on the sudo allowd cmds



www-data@gettingstarted:/var/www/html$ sudo /usr/bin/php --version
PHP 7.4.3 (cli) (built: Oct  6 2020 15:47:56) ( NTS )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
    with Zend OPcache v7.4.3, Copyright (c), by Zend Technologies
www-data@gettingstarted:/var/www/html$ 




1. Executing a PHP script:

To run a PHP file, provide the path to the `php` executable followed by the script's filename. 

Code

```
php /path/to/your/script.php
```


transferred over a reverse shell

connect to [10.10.14.141] from (UNKNOWN) [10.129.127.62] 46306
# whoami
root
# ifconfig
ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.129.127.62  netmask 255.255.0.0  broadcast 10.129.255.255
        inet6 dead:beef::250:56ff:feb0:105f  prefixlen 64  scopeid 0x0<global>
        inet6 fe80::250:56ff:feb0:105f  prefixlen 64  scopeid 0x20<link>
        ether 00:50:56:b0:10:5f  txqueuelen 1000  (Ethernet)
        RX packets 123972  bytes 8134282 (8.1 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 117827  bytes 9670845 (9.6 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 4702  bytes 371894 (371.8 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4702  bytes 371894 (371.8 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
